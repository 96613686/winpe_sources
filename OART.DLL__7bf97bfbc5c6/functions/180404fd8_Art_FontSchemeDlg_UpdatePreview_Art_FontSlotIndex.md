# Art::FontSchemeDlg::UpdatePreview(Art::FontSlotIndex)

- ea: `0x180404fd8`
- end: `0x180405379`
- name: `?UpdatePreview@FontSchemeDlg@Art@@AEAAXW4FontSlotIndex@2@@Z`
- size: `929`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180404efc`
- `0x18099b8ec`
- `0x18099bdb0`

## callees

- `0x180059bd4`
- `0x180059c40`
- `0x180071720`
- `0x1800902e8`
- `0x1800f4b68`
- `0x1803375ac`
- `0x180404fd8`
- `0x1804054d8`
- `0x1806a5084`
- `0x18099b798`
- `0x180a1b6bc`

## import_xrefs

- `mso40uiWin32Client!__imp_?CreateImage@FlexValue@FlexUI@@SA_NPEAUHBITMAP__@@AEAVFlexValueSP@2@EI_N2222@Z` at `0x180405242`
- `mso40uiWin32Client!__imp_?CreateImage@FlexValue@FlexUI@@SA_NPEAUHBITMAP__@@AEAVFlexValueSP@2@EI_N2222@Z` at `0x180405242`
- `mso40uiWin32Client!__imp_?MsoHbmpCreateCompatibleBitmap@@YAPEAUHBITMAP__@@PEAUHDC__@@HHPEAX@Z` at `0x18040516e`
- `mso40uiWin32Client!__imp_?MsoHbmpCreateCompatibleBitmap@@YAPEAUHBITMAP__@@PEAUHDC__@@HHPEAX@Z` at `0x18040516e`
- `mso40uiWin32Client!__imp_?SetGraphicScaleForDPI@FlexValue@FlexUI@@QEAAX_N@Z` at `0x180405253`
- `mso40uiWin32Client!__imp_?SetGraphicScaleForDPI@FlexValue@FlexUI@@QEAAX_N@Z` at `0x180405253`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x18040530f`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x18040531e`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x18040530f`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x18040531e`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180405126`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1804052d6`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180405126`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1804052d6`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1804051e2`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1804051e2`
- `GDI32!SelectObject` at `0x18040533d`
- `GDI32!SelectObject` at `0x18040533d`
- `GDI32!DeleteDC` at `0x180405346`
- `GDI32!DeleteDC` at `0x180405346`
- `USER32!GetDC` at `0x180405146`
- `USER32!GetDC` at `0x180405146`
- `USER32!ReleaseDC` at `0x180405357`
- `USER32!ReleaseDC` at `0x180405357`

## pseudocode

```c
void __fastcall Art::FontSchemeDlg::UpdatePreview(__int64 a1, int a2)
{
  __int64 v2; // rbx
  __int64 v4; // rsi
  __int64 *Checked; // rax
  __int64 v6; // rsi
  __int64 *v7; // rax
  __int64 *v8; // rdx
  __int64 v9; // r12
  HDC DC; // r14
  HBITMAP CompatibleBitmap; // r15
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  HDC v15; // rsi
  NetUI::BaseValue *v16; // rcx
  int v17; // ebx
  NetUI::BaseValue *v18; // rbx
  __int64 v19; // rdi
  __int64 v20; // r8
  HDC hdc[2]; // [rsp+50h] [rbp-30h] BYREF
  HDC v22; // [rsp+60h] [rbp-20h]
  __int128 v23; // [rsp+68h] [rbp-18h]
  NetUI::BaseValue *v24; // [rsp+B0h] [rbp+30h] BYREF
  HBITMAP v25; // [rsp+C0h] [rbp+40h]

  v2 = a2;
  v4 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  if ( dword_180E33870 > *(_DWORD *)(v4 + 32) )
  {
    Init_thread_header(&dword_180E33870);
    if ( dword_180E33870 == -1 )
    {
      dword_180E33874 = sub_18099B798(a1 + 56, 204);
      Init_thread_footer(&dword_180E33870);
    }
  }
  if ( dword_180E33878 > *(_DWORD *)(v4 + 32) )
  {
    Init_thread_header(&dword_180E33878);
    if ( dword_180E33878 == -1 )
    {
      dword_180E3387C = sub_18099B798(a1 + 56, 71);
      Init_thread_footer(&dword_180E33878);
    }
  }
  if ( dword_180E33880 > *(_DWORD *)(v4 + 32) )
  {
    Init_thread_header(&dword_180E33880);
    if ( dword_180E33880 == -1 )
    {
      dword_180E2E580 = dword_180E33874;
      dword_180E2E584 = dword_180E3387C;
      Init_thread_footer(&dword_180E33880);
    }
  }
  Checked = (__int64 *)Ofc::CProxyPtrImpl::GetChecked(*(Ofc::CProxyPtrImpl **)(a1 + 72));
  if ( (_DWORD)v2 )
  {
    if ( (_DWORD)v2 == 1 )
    {
      Checked += 4;
    }
    else
    {
      if ( (_DWORD)v2 != 2 )
      {
        MsoShipAssertTagProc(507824161);
        Ofc::CInvalidParamException::ThrowTag(0x1E44C820u);
        __debugbreak();
      }
      Checked += 8;
    }
  }
  v6 = *Checked;
  v7 = (__int64 *)Ofc::CProxyPtrImpl::GetChecked(*(Ofc::CProxyPtrImpl **)(a1 + 72));
  v8 = v7 + 16;
  if ( (_DWORD)v2 )
  {
    if ( (_DWORD)v2 == 1 )
      v8 = v7 + 20;
    else
      v8 = v7 + 24;
  }
  v9 = *v8;
  DC = GetDC(0);
  v22 = DC;
  v23 = 0;
  CompatibleBitmap = MsoHbmpCreateCompatibleBitmap(DC, dword_180E33874, dword_180E3387C, 0);
  v25 = CompatibleBitmap;
  if ( !CompatibleBitmap )
    Ofc::CLastErrorException::ThrowTag(0x13906CCu);
  *(_OWORD *)hdc = 0;
  Ofc::CCompatibleHDC::Create((Ofc::CCompatibleHDC *)hdc, DC, CompatibleBitmap);
  v12 = *(unsigned int *)(a1 + 4 * v2 + 104);
  if ( (int)v12 >= 0 && (int)v12 < *(_DWORD *)(a1 + 16 * v2 + 184) )
  {
    if ( (unsigned int)v12 < *(_DWORD *)(a1 + 16 * (v2 + 11) + 8) )
    {
      v13 = *(_QWORD *)(a1 + 16 * (v2 + 11)) + 24 * v12;
      goto LABEL_29;
    }
    CrashWithRecovery(0x1E892496u, 0);
  }
  v13 = 0;
LABEL_29:
  v14 = v6;
  v15 = hdc[0];
  Art::FontSchemeDlg::DrawPreview(a1 + 56, hdc[0], &qword_180E2E578, v14, v9, v13, v2);
  v24 = 0;
  FlexUI::FlexValue::CreateImage(CompatibleBitmap, (struct FlexUI::FlexValueSP *)&v24, 0, 0xFFFFFFFF, 0, 0, 0, 1, 0);
  v16 = v24;
  if ( v24 )
  {
    FlexUI::FlexValue::SetGraphicScaleForDPI(v24, 0);
    v16 = v24;
  }
  if ( !(_DWORD)v2 )
  {
    v18 = v16;
    v19 = *(_QWORD *)(a1 + 80);
    if ( v19 )
    {
      if ( !v16 )
        goto LABEL_48;
      NetUI::BaseValue::AddRef(v16);
      v20 = 3;
      goto LABEL_46;
    }
    goto LABEL_43;
  }
  v17 = v2 - 1;
  if ( v17 )
  {
    if ( v17 != 1 )
      goto LABEL_48;
    v18 = v16;
    v19 = *(_QWORD *)(a1 + 80);
    if ( v19 )
    {
      if ( v16 )
      {
        NetUI::BaseValue::AddRef(v16);
        v16 = v24;
        if ( v18 )
        {
          v20 = 9;
LABEL_46:
          (*(void (__fastcall **)(__int64, _QWORD, __int64, NetUI::BaseValue *))(*(_QWORD *)v19 + 48LL))(
            v19,
            0,
            v20,
            v18);
          NetUI::BaseValue::Release(v18);
          goto LABEL_47;
        }
      }
      goto LABEL_48;
    }
LABEL_43:
    MsoShipAssertTagProc(7997248);
LABEL_47:
    v16 = v24;
    goto LABEL_48;
  }
  v18 = v16;
  v19 = *(_QWORD *)(a1 + 80);
  if ( !v19 )
    goto LABEL_43;
  if ( v16 )
  {
    NetUI::BaseValue::AddRef(v16);
    v16 = v24;
    if ( v18 )
    {
      v20 = 6;
      goto LABEL_46;
    }
  }
LABEL_48:
  if ( v16 )
    NetUI::BaseValue::Release(v16);
  v24 = 0;
  if ( v15 )
  {
    if ( hdc[1] )
      SelectObject(v15, hdc[1]);
    DeleteDC(v15);
  }
  if ( DC )
    ReleaseDC(0, DC);
}

```

## disassembly

```asm
0x180404fd8  mov     [rsp-28h+arg_8], rbx
0x180404fdd  mov     [rsp-28h+arg_18], rsi
0x180404fe2  push    rbp
0x180404fe3  push    rdi
0x180404fe4  push    r12
0x180404fe6  push    r14
0x180404fe8  push    r15
0x180404fea  mov     rbp, rsp
0x180404fed  sub     rsp, 80h
0x180404ff4  movsxd  rbx, edx
0x180404ff7  mov     rdi, rcx
0x180404ffa  mov     r14d, 20h ; ' '
0x180405000  mov     r8d, cs:_tls_index
0x180405007  mov     rax, gs:58h
0x180405010  mov     rsi, [rax+r8*8]
0x180405014  mov     eax, [rsi+r14]
0x180405018  cmp     cs:dword_180E33870, eax
0x18040501e  jle     short loc_180405055
0x180405020  lea     rcx, dword_180E33870
0x180405027  call    _Init_thread_header
0x18040502c  cmp     cs:dword_180E33870, 0FFFFFFFFh
0x180405033  jnz     short loc_180405055
0x180405035  lea     rcx, [rdi+38h]
0x180405039  mov     edx, 0CCh
0x18040503e  call    sub_18099B798
0x180405043  mov     cs:dword_180E33874, eax
0x180405049  lea     rcx, dword_180E33870
0x180405050  call    _Init_thread_footer
0x180405055  mov     eax, [rsi+r14]
0x180405059  cmp     cs:dword_180E33878, eax
0x18040505f  jle     short loc_180405096
0x180405061  lea     rcx, dword_180E33878
0x180405068  call    _Init_thread_header
0x18040506d  cmp     cs:dword_180E33878, 0FFFFFFFFh
0x180405074  jnz     short loc_180405096
0x180405076  lea     rcx, [rdi+38h]
0x18040507a  mov     edx, 47h ; 'G'
0x18040507f  call    sub_18099B798
0x180405084  mov     cs:dword_180E3387C, eax
0x18040508a  lea     rcx, dword_180E33878
0x180405091  call    _Init_thread_footer
0x180405096  mov     eax, [rsi+r14]
0x18040509a  cmp     cs:dword_180E33880, eax
0x1804050a0  jle     short loc_1804050DB
0x1804050a2  lea     rcx, dword_180E33880
0x1804050a9  call    _Init_thread_header
0x1804050ae  cmp     cs:dword_180E33880, 0FFFFFFFFh
0x1804050b5  jnz     short loc_1804050DB
0x1804050b7  mov     eax, cs:dword_180E33874
0x1804050bd  mov     cs:dword_180E2E580, eax
0x1804050c3  mov     eax, cs:dword_180E3387C
0x1804050c9  mov     cs:dword_180E2E584, eax
0x1804050cf  lea     rcx, dword_180E33880
0x1804050d6  call    _Init_thread_footer
0x1804050db  mov     rcx, [rdi+48h]; this
0x1804050df  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1804050e4  mov     edx, ebx
0x1804050e6  test    ebx, ebx
0x1804050e8  jz      short loc_1804050FE
0x1804050ea  sub     edx, 1
0x1804050ed  jz      short loc_1804050FA
0x1804050ef  cmp     edx, 1
0x1804050f2  jnz     short loc_180405121
0x1804050f4  add     rax, 40h ; '@'
0x1804050f8  jmp     short loc_1804050FE
0x1804050fa  add     rax, 20h ; ' '
0x1804050fe  mov     rsi, [rax]
0x180405101  mov     rcx, [rdi+48h]; this
0x180405105  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x18040510a  lea     rdx, [rax+80h]
0x180405111  mov     ecx, ebx
0x180405113  test    ebx, ebx
0x180405115  jz      short loc_180405141
0x180405117  sub     ecx, 1
0x18040511a  jz      short loc_18040513D
0x18040511c  cmp     ecx, 1
0x18040511f  jz      short loc_180405137
0x180405121  mov     ecx, 1E44C821h
0x180405126  call    cs:__imp_MsoShipAssertTagProc
0x18040512c  mov     ecx, 1E44C820h; unsigned int
0x180405131  call    ?ThrowTag@CInvalidParamException@Ofc@@SAXK@Z; Ofc::CInvalidParamException::ThrowTag(ulong)
0x180405136  int     3; Trap to Debugger
0x180405137  add     rdx, 40h ; '@'
0x18040513b  jmp     short loc_180405141
0x18040513d  add     rdx, 20h ; ' '
0x180405141  mov     r12, [rdx]
0x180405144  xor     ecx, ecx; hWnd
0x180405146  call    cs:__imp_GetDC
0x18040514c  mov     r14, rax
0x18040514f  mov     [rbp+var_20], rax
0x180405153  xorps   xmm0, xmm0
0x180405156  movdqu  [rbp+var_18], xmm0
0x18040515b  xor     r9d, r9d
0x18040515e  mov     r8d, cs:dword_180E3387C
0x180405165  mov     edx, cs:dword_180E33874
0x18040516b  mov     rcx, rax
0x18040516e  call    cs:__imp_?MsoHbmpCreateCompatibleBitmap@@YAPEAUHBITMAP__@@PEAUHDC__@@HHPEAX@Z; MsoHbmpCreateCompatibleBitmap(HDC__ *,int,int,void *)
0x180405174  mov     r15, rax
0x180405177  mov     [rbp+arg_10], rax
0x18040517b  test    rax, rax
0x18040517e  jnz     short loc_18040518F
0x180405180  mov     ecx, 13906CCh; unsigned int
0x180405185  call    ?ThrowTag@CLastErrorException@Ofc@@SAXK@Z; Ofc::CLastErrorException::ThrowTag(ulong)
0x18040518a  nop
0x18040518b  jmp     short loc_18040518E
0x18040518e  nop
0x18040518f  xorps   xmm0, xmm0
0x180405192  movdqu  xmmword ptr [rbp+hdc], xmm0
0x180405197  mov     r8, r15; HBITMAP
0x18040519a  mov     rdx, r14; HDC
0x18040519d  lea     rcx, [rbp+hdc]; this
0x1804051a1  call    ?Create@CCompatibleHDC@Ofc@@QEAAXPEAUHDC__@@PEAUHBITMAP__@@@Z; Ofc::CCompatibleHDC::Create(HDC__ *,HBITMAP__ *)
0x1804051a6  mov     rdx, rbx
0x1804051a9  mov     ecx, [rdi+rbx*4+68h]
0x1804051ad  test    ecx, ecx
0x1804051af  js      short loc_1804051E9
0x1804051b1  mov     rax, rbx
0x1804051b4  add     rax, rax
0x1804051b7  cmp     ecx, [rdi+rax*8+0B8h]
0x1804051be  jge     short loc_1804051E9
0x1804051c0  add     rdx, 0Bh
0x1804051c4  add     rdx, rdx
0x1804051c7  cmp     ecx, [rdi+rdx*8+8]
0x1804051cb  jnb     short loc_1804051DB
0x1804051cd  lea     rcx, [rcx+rcx*2]
0x1804051d1  mov     rax, [rdi+rdx*8]
0x1804051d5  lea     rdx, [rax+rcx*8]
0x1804051d9  jmp     short loc_1804051EB
0x1804051db  xor     edx, edx
0x1804051dd  mov     ecx, 1E892496h
0x1804051e2  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1804051e8  nop
0x1804051e9  xor     edx, edx
0x1804051eb  lea     rcx, [rdi+38h]
0x1804051ef  mov     [rsp+80h+var_50], ebx
0x1804051f3  mov     [rsp+80h+var_58], rdx
0x1804051f8  mov     [rsp+80h+var_60], r12
0x1804051fd  mov     r9, rsi
0x180405200  lea     r8, qword_180E2E578
0x180405207  mov     rsi, [rbp+hdc]
0x18040520b  mov     rdx, rsi
0x18040520e  call    ?DrawPreview@FontSchemeDlg@Art@@CAXAEBV?$TWeakPtr@VUserInterface@Art@@@Ofc@@PEAUHDC__@@AEBUtagRECT@@PEB_W3PEBUFontPreviewData@2@W4FontSlotIndex@2@@Z; Art::FontSchemeDlg::DrawPreview(Ofc::TWeakPtr<Art::UserInterface> const &,HDC__ *,tagRECT const &,wchar_t const *,wchar_t const *,Art::FontPreviewData const *,Art::FontSlotIndex)
0x180405213  mov     [rbp+arg_0], 0
0x18040521b  mov     [rsp+80h+var_40], 0
0x180405220  mov     [rsp+80h+var_48], 1
0x180405225  mov     byte ptr [rsp+80h+var_50], 0
0x18040522a  mov     byte ptr [rsp+80h+var_58], 0
0x18040522f  mov     byte ptr [rsp+80h+var_60], 0
0x180405234  or      r9d, 0FFFFFFFFh
0x180405238  xor     r8d, r8d
0x18040523b  lea     rdx, [rbp+arg_0]
0x18040523f  mov     rcx, r15
0x180405242  call    cs:__imp_?CreateImage@FlexValue@FlexUI@@SA_NPEAUHBITMAP__@@AEAVFlexValueSP@2@EI_N2222@Z; FlexUI::FlexValue::CreateImage(HBITMAP__ *,FlexUI::FlexValueSP &,uchar,uint,bool,bool,bool,bool,bool)
0x180405248  mov     rcx, [rbp+arg_0]
0x18040524c  test    rcx, rcx
0x18040524f  jz      short loc_18040525D
0x180405251  xor     edx, edx
0x180405253  call    cs:__imp_?SetGraphicScaleForDPI@FlexValue@FlexUI@@QEAAX_N@Z; FlexUI::FlexValue::SetGraphicScaleForDPI(bool)
0x180405259  mov     rcx, [rbp+arg_0]; this
0x18040525d  test    ebx, ebx
0x18040525f  jz      short loc_1804052C5
0x180405261  sub     ebx, 1
0x180405264  jz      short loc_18040529E
0x180405266  cmp     ebx, 1
0x180405269  jnz     loc_180405319
0x18040526f  mov     rbx, rcx
0x180405272  mov     rdi, [rdi+50h]
0x180405276  test    rdi, rdi
0x180405279  jz      short loc_1804052D1
0x18040527b  test    rcx, rcx
0x18040527e  jz      loc_180405319
0x180405284  call    ?AddRef@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::AddRef(void)
0x180405289  mov     rcx, [rbp+arg_0]
0x18040528d  test    rbx, rbx
0x180405290  jz      loc_180405319
0x180405296  mov     r8d, 9
0x18040529c  jmp     short loc_1804052F7
0x18040529e  mov     rbx, rcx
0x1804052a1  mov     rdi, [rdi+50h]
0x1804052a5  test    rdi, rdi
0x1804052a8  jz      short loc_1804052D1
0x1804052aa  test    rcx, rcx
0x1804052ad  jz      short loc_180405319
0x1804052af  call    ?AddRef@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::AddRef(void)
0x1804052b4  mov     rcx, [rbp+arg_0]
0x1804052b8  test    rbx, rbx
0x1804052bb  jz      short loc_180405319
0x1804052bd  mov     r8d, 6
0x1804052c3  jmp     short loc_1804052F7
0x1804052c5  mov     rbx, rcx
0x1804052c8  mov     rdi, [rdi+50h]
0x1804052cc  test    rdi, rdi
0x1804052cf  jnz     short loc_1804052DE
0x1804052d1  mov     ecx, 7A0740h
0x1804052d6  call    cs:__imp_MsoShipAssertTagProc
0x1804052dc  jmp     short loc_180405315
0x1804052de  test    rbx, rbx
0x1804052e1  jz      short loc_180405319
0x1804052e3  call    ?AddRef@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::AddRef(void)
0x1804052e8  mov     rcx, [rbp+arg_0]
0x1804052ec  test    rbx, rbx
0x1804052ef  jz      short loc_180405319
0x1804052f1  mov     r8d, 3
0x1804052f7  mov     rax, [rdi]
0x1804052fa  mov     r9, rbx
0x1804052fd  xor     edx, edx
0x1804052ff  mov     rcx, rdi
0x180405302  mov     rax, [rax+30h]
0x180405306  call    cs:__guard_dispatch_icall_fptr
0x18040530c  mov     rcx, rbx
0x18040530f  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x180405315  mov     rcx, [rbp+arg_0]
0x180405319  test    rcx, rcx
0x18040531c  jz      short loc_180405324
0x18040531e  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x180405324  mov     [rbp+arg_0], 0
0x18040532c  test    rsi, rsi
0x18040532f  jz      short loc_18040534D
0x180405331  mov     rdx, [rbp+hdc+8]; h
0x180405335  test    rdx, rdx
0x180405338  jz      short loc_180405343
0x18040533a  mov     rcx, rsi; hdc
0x18040533d  call    cs:__imp_SelectObject
0x180405343  mov     rcx, rsi; hdc
0x180405346  call    cs:__imp_DeleteDC
0x18040534c  nop
0x18040534d  test    r14, r14
0x180405350  jz      short loc_18040535D
0x180405352  mov     rdx, r14; hDC
0x180405355  xor     ecx, ecx; hWnd
0x180405357  call    cs:__imp_ReleaseDC
0x18040535d  lea     r11, [rsp+80h+var_s0]
0x180405365  mov     rbx, [r11+38h]
0x180405369  mov     rsi, [r11+48h]
0x18040536d  mov     rsp, r11
0x180405370  pop     r15
0x180405372  pop     r14
0x180405374  pop     r12
0x180405376  pop     rdi
0x180405377  pop     rbp
0x180405378  retn
```
