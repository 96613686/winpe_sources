# Art::FontSchemeDlg::UpdatePreview(Art::FontSlotIndex)

- ea: `0x180467d2c`
- end: `0x1804680c9`
- name: `?UpdatePreview@FontSchemeDlg@Art@@AEAAXW4FontSlotIndex@2@@Z`
- size: `925`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180467c50`
- `0x1809a5a9c`
- `0x1809a5f60`

## callees

- `0x18000ee3c`
- `0x18000eea8`
- `0x180279050`
- `0x18029ab98`
- `0x1802c8bdc`
- `0x180435010`
- `0x180467d2c`
- `0x180468228`
- `0x1806bc4f0`
- `0x1809a5948`
- `0x180a2473c`

## import_xrefs

- `mso40uiWin32Client!__imp_?CreateImage@FlexValue@FlexUI@@SA_NPEAUHBITMAP__@@AEAVFlexValueSP@2@EI_N2222@Z` at `0x180467f92`
- `mso40uiWin32Client!__imp_?CreateImage@FlexValue@FlexUI@@SA_NPEAUHBITMAP__@@AEAVFlexValueSP@2@EI_N2222@Z` at `0x180467f92`
- `mso40uiWin32Client!__imp_?MsoHbmpCreateCompatibleBitmap@@YAPEAUHBITMAP__@@PEAUHDC__@@HHPEAX@Z` at `0x180467ebf`
- `mso40uiWin32Client!__imp_?MsoHbmpCreateCompatibleBitmap@@YAPEAUHBITMAP__@@PEAUHDC__@@HHPEAX@Z` at `0x180467ebf`
- `mso40uiWin32Client!__imp_?SetGraphicScaleForDPI@FlexValue@FlexUI@@QEAAX_N@Z` at `0x180467fa3`
- `mso40uiWin32Client!__imp_?SetGraphicScaleForDPI@FlexValue@FlexUI@@QEAAX_N@Z` at `0x180467fa3`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x18046805f`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x18046806e`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x18046805f`
- `mso40uiWin32Client!__imp_?Release@BaseValue@NetUI@@QEAAXXZ` at `0x18046806e`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180467e77`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180468026`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180467e77`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180468026`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180467f32`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180467f32`
- `GDI32!SelectObject` at `0x18046808d`
- `GDI32!SelectObject` at `0x18046808d`
- `GDI32!DeleteDC` at `0x180468096`
- `GDI32!DeleteDC` at `0x180468096`
- `USER32!GetDC` at `0x180467e97`
- `USER32!GetDC` at `0x180467e97`
- `USER32!ReleaseDC` at `0x1804680a7`
- `USER32!ReleaseDC` at `0x1804680a7`

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
  if ( dword_180E2D810 > *(_DWORD *)(v4 + 32) )
  {
    Init_thread_header(&dword_180E2D810);
    if ( dword_180E2D810 == -1 )
    {
      dword_180E2D814 = sub_1809A5948(a1 + 56, 204);
      Init_thread_footer(&dword_180E2D810);
    }
  }
  if ( dword_180E2D818 > *(_DWORD *)(v4 + 32) )
  {
    Init_thread_header(&dword_180E2D818);
    if ( dword_180E2D818 == -1 )
    {
      dword_180E2D81C = sub_1809A5948(a1 + 56, 71);
      Init_thread_footer(&dword_180E2D818);
    }
  }
  if ( dword_180E2D820 > *(_DWORD *)(v4 + 32) )
  {
    Init_thread_header(&dword_180E2D820);
    if ( dword_180E2D820 == -1 )
    {
      dword_180E2A960 = dword_180E2D814;
      dword_180E2A964 = dword_180E2D81C;
      Init_thread_footer(&dword_180E2D820);
    }
  }
  Checked = (__int64 *)Ofc::CProxyPtrImpl::GetChecked(*(Ofc::CProxyPtrImpl **)(a1 + 72));
  if ( (_DWORD)v2 )
  {
    if ( (_DWORD)v2 == 1 )
    {
      Checked += 3;
    }
    else
    {
      if ( (_DWORD)v2 != 2 )
      {
        MsoShipAssertTagProc(507824161);
        Ofc::CInvalidParamException::ThrowTag(0x1E44C820u);
        __debugbreak();
      }
      Checked += 6;
    }
  }
  v6 = *Checked;
  v7 = (__int64 *)Ofc::CProxyPtrImpl::GetChecked(*(Ofc::CProxyPtrImpl **)(a1 + 72));
  v8 = v7 + 13;
  if ( (_DWORD)v2 )
  {
    if ( (_DWORD)v2 == 1 )
      v8 = v7 + 16;
    else
      v8 = v7 + 19;
  }
  v9 = *v8;
  DC = GetDC(0);
  v22 = DC;
  v23 = 0;
  CompatibleBitmap = MsoHbmpCreateCompatibleBitmap(DC, dword_180E2D814, dword_180E2D81C, 0);
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
  Art::FontSchemeDlg::DrawPreview(a1 + 56, hdc[0], &qword_180E2A958, v14, v9, v13, v2);
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
0x180467d2c  mov     [rsp-28h+arg_8], rbx
0x180467d31  mov     [rsp-28h+arg_18], rsi
0x180467d36  push    rbp
0x180467d37  push    rdi
0x180467d38  push    r12
0x180467d3a  push    r14
0x180467d3c  push    r15
0x180467d3e  mov     rbp, rsp
0x180467d41  sub     rsp, 80h
0x180467d48  movsxd  rbx, edx
0x180467d4b  mov     rdi, rcx
0x180467d4e  mov     r14d, 20h ; ' '
0x180467d54  mov     r8d, cs:_tls_index
0x180467d5b  mov     rax, gs:58h
0x180467d64  mov     rsi, [rax+r8*8]
0x180467d68  mov     eax, [rsi+r14]
0x180467d6c  cmp     cs:dword_180E2D810, eax
0x180467d72  jle     short loc_180467DA9
0x180467d74  lea     rcx, dword_180E2D810
0x180467d7b  call    _Init_thread_header
0x180467d80  cmp     cs:dword_180E2D810, 0FFFFFFFFh
0x180467d87  jnz     short loc_180467DA9
0x180467d89  lea     rcx, [rdi+38h]
0x180467d8d  mov     edx, 0CCh
0x180467d92  call    sub_1809A5948
0x180467d97  mov     cs:dword_180E2D814, eax
0x180467d9d  lea     rcx, dword_180E2D810
0x180467da4  call    _Init_thread_footer
0x180467da9  mov     eax, [rsi+r14]
0x180467dad  cmp     cs:dword_180E2D818, eax
0x180467db3  jle     short loc_180467DEA
0x180467db5  lea     rcx, dword_180E2D818
0x180467dbc  call    _Init_thread_header
0x180467dc1  cmp     cs:dword_180E2D818, 0FFFFFFFFh
0x180467dc8  jnz     short loc_180467DEA
0x180467dca  lea     rcx, [rdi+38h]
0x180467dce  mov     edx, 47h ; 'G'
0x180467dd3  call    sub_1809A5948
0x180467dd8  mov     cs:dword_180E2D81C, eax
0x180467dde  lea     rcx, dword_180E2D818
0x180467de5  call    _Init_thread_footer
0x180467dea  mov     eax, [rsi+r14]
0x180467dee  cmp     cs:dword_180E2D820, eax
0x180467df4  jle     short loc_180467E2F
0x180467df6  lea     rcx, dword_180E2D820
0x180467dfd  call    _Init_thread_header
0x180467e02  cmp     cs:dword_180E2D820, 0FFFFFFFFh
0x180467e09  jnz     short loc_180467E2F
0x180467e0b  mov     eax, cs:dword_180E2D814
0x180467e11  mov     cs:dword_180E2A960, eax
0x180467e17  mov     eax, cs:dword_180E2D81C
0x180467e1d  mov     cs:dword_180E2A964, eax
0x180467e23  lea     rcx, dword_180E2D820
0x180467e2a  call    _Init_thread_footer
0x180467e2f  mov     rcx, [rdi+48h]; this
0x180467e33  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x180467e38  mov     edx, ebx
0x180467e3a  test    ebx, ebx
0x180467e3c  jz      short loc_180467E52
0x180467e3e  sub     edx, 1
0x180467e41  jz      short loc_180467E4E
0x180467e43  cmp     edx, 1
0x180467e46  jnz     short loc_180467E72
0x180467e48  add     rax, 30h ; '0'
0x180467e4c  jmp     short loc_180467E52
0x180467e4e  add     rax, 18h
0x180467e52  mov     rsi, [rax]
0x180467e55  mov     rcx, [rdi+48h]; this
0x180467e59  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x180467e5e  lea     rdx, [rax+68h]
0x180467e62  mov     ecx, ebx
0x180467e64  test    ebx, ebx
0x180467e66  jz      short loc_180467E92
0x180467e68  sub     ecx, 1
0x180467e6b  jz      short loc_180467E8E
0x180467e6d  cmp     ecx, 1
0x180467e70  jz      short loc_180467E88
0x180467e72  mov     ecx, 1E44C821h
0x180467e77  call    cs:__imp_MsoShipAssertTagProc
0x180467e7d  mov     ecx, 1E44C820h; unsigned int
0x180467e82  call    ?ThrowTag@CInvalidParamException@Ofc@@SAXK@Z; Ofc::CInvalidParamException::ThrowTag(ulong)
0x180467e87  int     3; Trap to Debugger
0x180467e88  add     rdx, 30h ; '0'
0x180467e8c  jmp     short loc_180467E92
0x180467e8e  add     rdx, 18h
0x180467e92  mov     r12, [rdx]
0x180467e95  xor     ecx, ecx; hWnd
0x180467e97  call    cs:__imp_GetDC
0x180467e9d  mov     r14, rax
0x180467ea0  mov     [rbp+var_20], rax
0x180467ea4  xorps   xmm0, xmm0
0x180467ea7  movdqu  [rbp+var_18], xmm0
0x180467eac  xor     r9d, r9d
0x180467eaf  mov     r8d, cs:dword_180E2D81C
0x180467eb6  mov     edx, cs:dword_180E2D814
0x180467ebc  mov     rcx, rax
0x180467ebf  call    cs:__imp_?MsoHbmpCreateCompatibleBitmap@@YAPEAUHBITMAP__@@PEAUHDC__@@HHPEAX@Z; MsoHbmpCreateCompatibleBitmap(HDC__ *,int,int,void *)
0x180467ec5  mov     r15, rax
0x180467ec8  mov     [rbp+arg_10], rax
0x180467ecc  test    rax, rax
0x180467ecf  jnz     short loc_180467EDF
0x180467ed1  mov     ecx, 13906CCh; unsigned int
0x180467ed6  call    ?ThrowTag@CLastErrorException@Ofc@@SAXK@Z; Ofc::CLastErrorException::ThrowTag(ulong)
0x180467edb  nop
0x180467edc  jmp     short $+2
0x180467ede  nop
0x180467edf  xorps   xmm0, xmm0
0x180467ee2  movdqu  xmmword ptr [rbp+hdc], xmm0
0x180467ee7  mov     r8, r15; HBITMAP
0x180467eea  mov     rdx, r14; HDC
0x180467eed  lea     rcx, [rbp+hdc]; this
0x180467ef1  call    ?Create@CCompatibleHDC@Ofc@@QEAAXPEAUHDC__@@PEAUHBITMAP__@@@Z; Ofc::CCompatibleHDC::Create(HDC__ *,HBITMAP__ *)
0x180467ef6  mov     rdx, rbx
0x180467ef9  mov     ecx, [rdi+rbx*4+68h]
0x180467efd  test    ecx, ecx
0x180467eff  js      short loc_180467F39
0x180467f01  mov     rax, rbx
0x180467f04  add     rax, rax
0x180467f07  cmp     ecx, [rdi+rax*8+0B8h]
0x180467f0e  jge     short loc_180467F39
0x180467f10  add     rdx, 0Bh
0x180467f14  add     rdx, rdx
0x180467f17  cmp     ecx, [rdi+rdx*8+8]
0x180467f1b  jnb     short loc_180467F2B
0x180467f1d  lea     rcx, [rcx+rcx*2]
0x180467f21  mov     rax, [rdi+rdx*8]
0x180467f25  lea     rdx, [rax+rcx*8]
0x180467f29  jmp     short loc_180467F3B
0x180467f2b  xor     edx, edx
0x180467f2d  mov     ecx, 1E892496h
0x180467f32  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180467f38  nop
0x180467f39  xor     edx, edx
0x180467f3b  lea     rcx, [rdi+38h]
0x180467f3f  mov     [rsp+80h+var_50], ebx
0x180467f43  mov     [rsp+80h+var_58], rdx
0x180467f48  mov     [rsp+80h+var_60], r12
0x180467f4d  mov     r9, rsi
0x180467f50  lea     r8, qword_180E2A958
0x180467f57  mov     rsi, [rbp+hdc]
0x180467f5b  mov     rdx, rsi
0x180467f5e  call    ?DrawPreview@FontSchemeDlg@Art@@CAXAEBV?$TWeakPtr@VUserInterface@Art@@@Ofc@@PEAUHDC__@@AEBUtagRECT@@PEB_W3PEBUFontPreviewData@2@W4FontSlotIndex@2@@Z; Art::FontSchemeDlg::DrawPreview(Ofc::TWeakPtr<Art::UserInterface> const &,HDC__ *,tagRECT const &,wchar_t const *,wchar_t const *,Art::FontPreviewData const *,Art::FontSlotIndex)
0x180467f63  mov     [rbp+arg_0], 0
0x180467f6b  mov     [rsp+80h+var_40], 0
0x180467f70  mov     [rsp+80h+var_48], 1
0x180467f75  mov     byte ptr [rsp+80h+var_50], 0
0x180467f7a  mov     byte ptr [rsp+80h+var_58], 0
0x180467f7f  mov     byte ptr [rsp+80h+var_60], 0
0x180467f84  or      r9d, 0FFFFFFFFh
0x180467f88  xor     r8d, r8d
0x180467f8b  lea     rdx, [rbp+arg_0]
0x180467f8f  mov     rcx, r15
0x180467f92  call    cs:__imp_?CreateImage@FlexValue@FlexUI@@SA_NPEAUHBITMAP__@@AEAVFlexValueSP@2@EI_N2222@Z; FlexUI::FlexValue::CreateImage(HBITMAP__ *,FlexUI::FlexValueSP &,uchar,uint,bool,bool,bool,bool,bool)
0x180467f98  mov     rcx, [rbp+arg_0]
0x180467f9c  test    rcx, rcx
0x180467f9f  jz      short loc_180467FAD
0x180467fa1  xor     edx, edx
0x180467fa3  call    cs:__imp_?SetGraphicScaleForDPI@FlexValue@FlexUI@@QEAAX_N@Z; FlexUI::FlexValue::SetGraphicScaleForDPI(bool)
0x180467fa9  mov     rcx, [rbp+arg_0]; this
0x180467fad  test    ebx, ebx
0x180467faf  jz      short loc_180468015
0x180467fb1  sub     ebx, 1
0x180467fb4  jz      short loc_180467FEE
0x180467fb6  cmp     ebx, 1
0x180467fb9  jnz     loc_180468069
0x180467fbf  mov     rbx, rcx
0x180467fc2  mov     rdi, [rdi+50h]
0x180467fc6  test    rdi, rdi
0x180467fc9  jz      short loc_180468021
0x180467fcb  test    rcx, rcx
0x180467fce  jz      loc_180468069
0x180467fd4  call    ?AddRef@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::AddRef(void)
0x180467fd9  mov     rcx, [rbp+arg_0]
0x180467fdd  test    rbx, rbx
0x180467fe0  jz      loc_180468069
0x180467fe6  mov     r8d, 9
0x180467fec  jmp     short loc_180468047
0x180467fee  mov     rbx, rcx
0x180467ff1  mov     rdi, [rdi+50h]
0x180467ff5  test    rdi, rdi
0x180467ff8  jz      short loc_180468021
0x180467ffa  test    rcx, rcx
0x180467ffd  jz      short loc_180468069
0x180467fff  call    ?AddRef@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::AddRef(void)
0x180468004  mov     rcx, [rbp+arg_0]
0x180468008  test    rbx, rbx
0x18046800b  jz      short loc_180468069
0x18046800d  mov     r8d, 6
0x180468013  jmp     short loc_180468047
0x180468015  mov     rbx, rcx
0x180468018  mov     rdi, [rdi+50h]
0x18046801c  test    rdi, rdi
0x18046801f  jnz     short loc_18046802E
0x180468021  mov     ecx, 7A0740h
0x180468026  call    cs:__imp_MsoShipAssertTagProc
0x18046802c  jmp     short loc_180468065
0x18046802e  test    rbx, rbx
0x180468031  jz      short loc_180468069
0x180468033  call    ?AddRef@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::AddRef(void)
0x180468038  mov     rcx, [rbp+arg_0]
0x18046803c  test    rbx, rbx
0x18046803f  jz      short loc_180468069
0x180468041  mov     r8d, 3
0x180468047  mov     rax, [rdi]
0x18046804a  mov     r9, rbx
0x18046804d  xor     edx, edx
0x18046804f  mov     rcx, rdi
0x180468052  mov     rax, [rax+30h]
0x180468056  call    cs:__guard_dispatch_icall_fptr
0x18046805c  mov     rcx, rbx
0x18046805f  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x180468065  mov     rcx, [rbp+arg_0]
0x180468069  test    rcx, rcx
0x18046806c  jz      short loc_180468074
0x18046806e  call    cs:__imp_?Release@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::Release(void)
0x180468074  mov     [rbp+arg_0], 0
0x18046807c  test    rsi, rsi
0x18046807f  jz      short loc_18046809D
0x180468081  mov     rdx, [rbp+hdc+8]; h
0x180468085  test    rdx, rdx
0x180468088  jz      short loc_180468093
0x18046808a  mov     rcx, rsi; hdc
0x18046808d  call    cs:__imp_SelectObject
0x180468093  mov     rcx, rsi; hdc
0x180468096  call    cs:__imp_DeleteDC
0x18046809c  nop
0x18046809d  test    r14, r14
0x1804680a0  jz      short loc_1804680AD
0x1804680a2  mov     rdx, r14; hDC
0x1804680a5  xor     ecx, ecx; hWnd
0x1804680a7  call    cs:__imp_ReleaseDC
0x1804680ad  lea     r11, [rsp+80h+var_s0]
0x1804680b5  mov     rbx, [r11+38h]
0x1804680b9  mov     rsi, [r11+48h]
0x1804680bd  mov     rsp, r11
0x1804680c0  pop     r15
0x1804680c2  pop     r14
0x1804680c4  pop     r12
0x1804680c6  pop     rdi
0x1804680c7  pop     rbp
0x1804680c8  retn
```
