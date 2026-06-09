# Jot::CTutorialFrame::CTutorialFrame(MsoCF::AFrameApp &,Jot::AMainApp &)

- ea: `0x140114d24`
- end: `0x140115229`
- name: `??0CTutorialFrame@Jot@@QEAA@AEAUAFrameApp@MsoCF@@AEAUAMainApp@1@@Z`
- size: `1285`
- prototype: `__int64 __fastcall(Jot::CTutorialFrame *__hidden this, struct MsoCF::AFrameApp *, struct Jot::AMainApp *)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update`

## callers

- `0x14011b5c4`

## callees

- `0x1400091c8`
- `0x14000968c`
- `0x14000cd04`
- `0x14000ce30`
- `0x14000ea38`
- `0x1400209a0`
- `0x14003f250`
- `0x1400408d0`
- `0x140056ac0`
- `0x140057580`
- `0x140069594`
- `0x140114d24`
- `0x140116d68`

## import_xrefs

- `onmain!?priPageTitleVisible@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B` at `0x1401150a2`
- `onmain!?GetEmpty@AWorkspaceDependencyFactory@Jot@@SAAEBU12@XZ` at `0x140114fa0`
- `onmain!?GetEmpty@AWorkspaceDependencyFactory@Jot@@SAAEBU12@XZ` at `0x140114fa0`
- `onmain!?Capacity@CWzInBuffer@Jot@@QEBAHXZ` at `0x140114e76`
- `onmain!?Capacity@CWzInBuffer@Jot@@QEBAHXZ` at `0x140114e76`
- `onmain!??BCWzInBuffer@Jot@@QEAAPEA_WXZ` at `0x140114e3d`
- `onmain!??BCWzInBuffer@Jot@@QEAAPEA_WXZ` at `0x140114e85`
- `onmain!??BCWzInBuffer@Jot@@QEAAPEA_WXZ` at `0x140114ea9`
- `onmain!??BCWzInBuffer@Jot@@QEAAPEA_WXZ` at `0x140114e3d`
- `onmain!??BCWzInBuffer@Jot@@QEAAPEA_WXZ` at `0x140114e85`
- `onmain!??BCWzInBuffer@Jot@@QEAAPEA_WXZ` at `0x140114ea9`
- `onmain!?CreatePropertySet@MsoCF@@YA?AV?$CIPtr@UIPropertySet@MsoCF@@U12@@1@PEAUIPropertySet@1@@Z` at `0x140115089`
- `onmain!?CreatePropertySet@MsoCF@@YA?AV?$CIPtr@UIPropertySet@MsoCF@@U12@@1@PEAUIPropertySet@1@@Z` at `0x140115089`
- `USER32!GetWindowRect` at `0x1401151a0`
- `USER32!GetWindowRect` at `0x1401151a0`
- `USER32!GetWindowLongW` at `0x140114ef9`
- `USER32!GetWindowLongW` at `0x140114ef9`
- `USER32!LoadIconW` at `0x140114e29`
- `USER32!LoadIconW` at `0x140114e29`
- `USER32!SetWindowLongW` at `0x140114f20`
- `USER32!SetWindowLongW` at `0x140114f20`
- `USER32!RegisterWindowMessageW` at `0x14011515c`
- `USER32!RegisterWindowMessageW` at `0x14011515c`
- `Mso20Win32Client!__imp_?MsoFRegReadWz@@YAHPEBU_msoreg@@PEA_WK@Z` at `0x140114e98`
- `Mso20Win32Client!__imp_?MsoFRegReadWz@@YAHPEBU_msoreg@@PEA_WK@Z` at `0x140114e98`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x140114edb`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x140115000`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x140114edb`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x140115000`

## string_xrefs

- `0x140115155`: `WM_JOT_MAINTHREAD_APC`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
Jot::CTutorialFrame *__fastcall Jot::CTutorialFrame::CTutorialFrame(
        Jot::CTutorialFrame *this,
        struct MsoCF::AFrameApp *a2,
        struct Jot::AMainApp *a3)
{
  unsigned int v6; // ebx
  wchar_t *v7; // rax
  __int64 v8; // rax
  HWND v9; // rax
  LONG v10; // ebx
  HWND v11; // rax
  __int64 v12; // rax
  __int64 v13; // r8
  __int64 (__fastcall *v14)(struct Jot::AMainApp *, _QWORD *, Jot::CTutorialFrame *, __int64, __int128 *, char *, __int64); // rbx
  __int64 Empty; // rax
  __int64 v16; // r9
  __int64 v17; // rax
  _QWORD *v18; // r14
  __int64 v19; // rcx
  __int64 v20; // rdi
  void (__fastcall *v21)(__int64, _QWORD); // rbx
  _QWORD *v22; // rax
  __int64 v23; // rax
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  HWND v28; // rax
  _BYTE v30[8]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v31; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v32[2]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v33[5]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v34; // [rsp+88h] [rbp-78h]
  int v35; // [rsp+8Ch] [rbp-74h]
  __int64 v36; // [rsp+90h] [rbp-70h]
  __int16 v37; // [rsp+98h] [rbp-68h]
  __int16 v38; // [rsp+9Ah] [rbp-66h]
  _OWORD v39[2]; // [rsp+9Ch] [rbp-64h] BYREF
  int v40; // [rsp+BCh] [rbp-44h]
  Jot::CTutorialFrame *v41; // [rsp+C0h] [rbp-40h]
  _BYTE v42[40]; // [rsp+C8h] [rbp-38h] BYREF
  struct tagRECT Rect; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v44; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v45[368]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v46[4272]; // [rsp+280h] [rbp+180h] BYREF

  v41 = this;
  Jot::CJotFrameBase::CJotFrameBase(this);
  *(_QWORD *)this = &Jot::CTutorialFrame::`vftable';
  *((_QWORD *)this + 25) = &Jot::CTutorialFrame::XFrameUser::`vftable';
  *((_QWORD *)this + 26) = &Jot::CTutorialFrame::XWorkspaceUser::`vftable';
  *((_QWORD *)this + 27) = &Jot::CTutorialFrame::XToolbarSetUser::`vftable';
  *((_QWORD *)this + 28) = 0;
  *((_QWORD *)this + 29) = 0;
  *((_QWORD *)this + 30) = 0;
  *((_QWORD *)this + 38) = 0;
  *((_WORD *)this + 156) = 0;
  *((_BYTE *)this + 314) = 0;
  *(_QWORD *)((char *)this + 316) = 0;
  *((_QWORD *)this + 43) = 0;
  Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(
    v45,
    *((_QWORD *)Jot::CJotApp::s_pSingletonJotApp + 62),
    645739117);
  v36 = 0;
  v38 = 0;
  memset(v39, 0, sizeof(v39));
  v40 = 0;
  v33[0] = LoadIconW(*((HINSTANCE *)Jot::CJotApp::s_pSingletonJotApp + 34), (LPCWSTR)1);
  v33[1] = 0;
  v33[2] = Jot::CWzInBuffer::operator wchar_t *(v45);
  v33[3] = 0;
  v37 = 256;
  v33[4] = 0;
  v34 = 0x80000000;
  v35 = 0;
  Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2083>>,2082>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2083>>,2082>(v46);
  v6 = Jot::CWzInBuffer::Capacity((Jot::CWzInBuffer *)v46);
  v7 = (wchar_t *)Jot::CWzInBuffer::operator wchar_t *(v46);
  if ( MsoFRegReadWz((const struct _msoreg *)&vmsoridCUBrandOneNoteName, v7, v6) )
    *(_QWORD *)((char *)v39 + 12) = Jot::CWzInBuffer::operator wchar_t *(v46);
  v8 = (*(__int64 (__fastcall **)(struct MsoCF::AFrameApp *, _QWORD *))(*(_QWORD *)a2 + 16LL))(a2, v33);
  *((_QWORD *)this + 13) = v8;
  if ( !v8 )
  {
    CrashWithRecovery(0x1E42339Cu, 0);
    __debugbreak();
  }
  v9 = (HWND)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 120LL))(v8);
  v10 = GetWindowLongW(v9, -16) & 0xFF30FFFF;
  v11 = (HWND)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 13) + 120LL))(*((_QWORD *)this + 13));
  SetWindowLongW(v11, -16, v10);
  (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 13) + 96LL))(*((_QWORD *)this + 13), (char *)this + 200);
  (*(void (__fastcall **)(_QWORD, Jot::CTutorialFrame *))(**((_QWORD **)this + 13) + 136LL))(
    *((_QWORD *)this + 13),
    this);
  (*(void (__fastcall **)(Jot::CTutorialFrame *, _QWORD))(*(_QWORD *)this + 144LL))(
    this,
    *((_QWORD *)Jot::CJotApp::s_pSingletonJotApp + 34));
  v12 = (***((__int64 (__fastcall ****)(_QWORD))this + 13))(*((_QWORD *)this + 13));
  LOBYTE(v13) = 1;
  (*(void (__fastcall **)(__int64, Jot::CTutorialFrame *, __int64))(*(_QWORD *)v12 + 16LL))(v12, this, v13);
  v14 = *(__int64 (__fastcall **)(struct Jot::AMainApp *, _QWORD *, Jot::CTutorialFrame *, __int64, __int128 *, char *, __int64))(*(_QWORD *)a3 + 8LL);
  Empty = Jot::AWorkspaceDependencyFactory::GetEmpty();
  v44 = 0;
  LOBYTE(v16) = 1;
  v17 = v14(a3, v32, this, v16, &v44, (char *)this + 208, Empty);
  v18 = (_QWORD *)((char *)this + 112);
  std::unique_ptr<Jot::AWorkspace>::operator=<std::default_delete<Jot::AWorkspace>,0>((char *)this + 112, v17);
  std::unique_ptr<Jot::ANavigationWindowElement>::~unique_ptr<Jot::ANavigationWindowElement>(v32);
  v19 = *((_QWORD *)this + 14);
  if ( !v19 )
  {
    CrashWithRecovery(0x1E42339Au, 0);
    __debugbreak();
  }
  *((_QWORD *)this + 20) = this;
  v20 = *((_QWORD *)this + 13);
  v21 = *(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v20 + 48LL);
  v22 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v19 + 32LL))(v19, v32);
  v21(v20, *v22);
  if ( v32[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v32[0] + 16LL))(v32[0]);
  v23 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v18 + 16LL))(*v18, v42);
  Mso::LegacyFuture<unsigned int>::Get(v23);
  Jot::FastIntegration::Future<void>::~Future<void>(v42);
  Jot::CTutorialFrame::UpdateContainedHwnds(this);
  MsoCF::CreatePropertySet(&v31, 0);
  v30[0] = 0;
  (*(void (__fastcall **)(__int64, _QWORD, _BYTE *))(*(_QWORD *)v31 + 56LL))(
    v31,
    Jot::PropertySpace_JotMain::priPageTitleVisible,
    v30);
  (*(void (__fastcall **)(_QWORD, __int64, __int64, __int64))(**((_QWORD **)this + 13) + 64LL))(
    *((_QWORD *)this + 13),
    131731,
    v31,
    1);
  if ( *v18 )
    v25 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v18 + 160LL))(*v18);
  else
    v25 = 0;
  if ( v25 )
    v26 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v25 + 8LL))(v25);
  else
    v26 = 0;
  if ( v26 )
    v27 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 400LL))(v26);
  else
    v27 = 0;
  if ( v27 )
  {
    LOBYTE(v24) = 1;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v27 + 200LL))(v27, v24);
  }
  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v18 + 656LL))(*v18);
  WM_JOT_TUTORIAL_MAINTHREAD_APC = RegisterWindowMessageW(L"WM_JOT_MAINTHREAD_APC");
  (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 13) + 176LL))(*((_QWORD *)this + 13), 5);
  v28 = (HWND)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 13) + 120LL))(*((_QWORD *)this + 13));
  Rect = 0;
  GetWindowRect(v28, &Rect);
  *((_DWORD *)this + 79) = Rect.right - Rect.left;
  *((_DWORD *)this + 80) = Rect.bottom - Rect.top;
  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v18 + 88LL))(*v18);
  if ( v31 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>::~CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>(v46);
  Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>::~CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>(v45);
  return this;
}

```

## disassembly

```asm
0x140114d24  mov     [rsp-8+arg_18], rbx
0x140114d29  push    rbp
0x140114d2a  push    rsi
0x140114d2b  push    rdi
0x140114d2c  push    r12
0x140114d2e  push    r13
0x140114d30  push    r14
0x140114d32  push    r15
0x140114d34  lea     rbp, [rsp-1240h]
0x140114d3c  mov     eax, 1340h
0x140114d41  call    _alloca_probe
0x140114d46  sub     rsp, rax
0x140114d49  mov     rax, cs:__security_cookie
0x140114d50  xor     rax, rsp
0x140114d53  mov     [rbp+1270h+var_40], rax
0x140114d5a  mov     r12, r8
0x140114d5d  mov     rdi, rdx
0x140114d60  mov     rsi, rcx
0x140114d63  mov     [rbp+1270h+var_12B0], rcx
0x140114d67  call    ??0CJotFrameBase@Jot@@IEAA@XZ; Jot::CJotFrameBase::CJotFrameBase(void)
0x140114d6c  lea     rax, ??_7CTutorialFrame@Jot@@6B@; const Jot::CTutorialFrame::`vftable'
0x140114d73  mov     [rsi], rax
0x140114d76  lea     r14, [rsi+0C8h]
0x140114d7d  lea     rax, ??_7XFrameUser@CTutorialFrame@Jot@@6B@; const Jot::CTutorialFrame::XFrameUser::`vftable'
0x140114d84  mov     [r14], rax
0x140114d87  lea     r15, [rsi+0D0h]
0x140114d8e  lea     rax, ??_7XWorkspaceUser@CTutorialFrame@Jot@@6B@; const Jot::CTutorialFrame::XWorkspaceUser::`vftable'
0x140114d95  mov     [r15], rax
0x140114d98  lea     rax, ??_7XToolbarSetUser@CTutorialFrame@Jot@@6B@; const Jot::CTutorialFrame::XToolbarSetUser::`vftable'
0x140114d9f  mov     [rsi+0D8h], rax
0x140114da6  xor     r13d, r13d
0x140114da9  mov     [rsi+0E0h], r13
0x140114db0  mov     [rsi+0E8h], r13
0x140114db7  mov     [rsi+0F0h], r13
0x140114dbe  mov     [rsi+130h], r13
0x140114dc5  mov     [rsi+138h], r13w
0x140114dcd  mov     [rsi+13Ah], r13b
0x140114dd4  mov     [rsi+13Ch], r13
0x140114ddb  mov     [rsi+158h], r13
0x140114de2  mov     r8d, 267D326Dh
0x140114de8  mov     rdx, cs:?s_pSingletonJotApp@CJotApp@Jot@@0PEAV12@EA; Jot::CJotApp * Jot::CJotApp::s_pSingletonJotApp
0x140114def  mov     rdx, [rdx+1F0h]
0x140114df6  lea     rcx, [rbp+1270h+var_1260]
0x140114dfa  call    ??0?$CWzInBuffer_T@V?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CFastBuffer@_W$0IB@@2@@MsoCF@@$0IA@@Jot@@QEAA@PEAUHINSTANCE__@@I@Z; Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(HINSTANCE__ *,uint)
0x140114dff  mov     [rbp+1270h+var_12E0], r13
0x140114e03  mov     [rbp+1270h+var_12D6], r13w
0x140114e08  xor     eax, eax
0x140114e0a  xorps   xmm0, xmm0
0x140114e0d  movups  [rbp+1270h+var_12D4], xmm0
0x140114e11  movups  [rbp+1270h+var_12C4], xmm0
0x140114e15  mov     [rbp+1270h+var_12B4], eax
0x140114e18  lea     edx, [rax+1]; lpIconName
0x140114e1b  mov     rcx, cs:?s_pSingletonJotApp@CJotApp@Jot@@0PEAV12@EA; Jot::CJotApp * Jot::CJotApp::s_pSingletonJotApp
0x140114e22  mov     rcx, [rcx+110h]; hInstance
0x140114e29  call    cs:__imp_LoadIconW
0x140114e2f  mov     [rsp+1370h+var_1310], rax
0x140114e34  mov     [rsp+1370h+var_1308], r13
0x140114e39  lea     rcx, [rbp+1270h+var_1260]
0x140114e3d  call    cs:__imp_??BCWzInBuffer@Jot@@QEAAPEA_WXZ; Jot::CWzInBuffer::operator wchar_t *(void)
0x140114e43  mov     [rsp+1370h+var_1300], rax
0x140114e48  mov     [rsp+1370h+var_12F8], r13
0x140114e4d  mov     [rbp+1270h+var_12D8], 100h
0x140114e53  mov     [rbp+1270h+var_12F0], r13
0x140114e57  mov     [rbp+1270h+var_12E8], 80000000h
0x140114e5e  mov     [rbp+1270h+var_12E4], r13d
0x140114e62  lea     rcx, [rbp+1270h+var_10F0]
0x140114e69  call    ??0?$CWzInBuffer_T@V?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CFastBuffer@_W$0ICD@@2@@MsoCF@@$0ICC@@Jot@@QEAA@XZ; Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2083>>,2082>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2083>>,2082>(void)
0x140114e6e  nop
0x140114e6f  lea     rcx, [rbp+1270h+var_10F0]
0x140114e76  call    cs:__imp_?Capacity@CWzInBuffer@Jot@@QEBAHXZ; Jot::CWzInBuffer::Capacity(void)
0x140114e7c  mov     ebx, eax
0x140114e7e  lea     rcx, [rbp+1270h+var_10F0]
0x140114e85  call    cs:__imp_??BCWzInBuffer@Jot@@QEAAPEA_WXZ; Jot::CWzInBuffer::operator wchar_t *(void)
0x140114e8b  mov     r8d, ebx
0x140114e8e  mov     rdx, rax
0x140114e91  lea     rcx, ?vmsoridCUBrandOneNoteName@@3U_msoreg@@B; _msoreg const vmsoridCUBrandOneNoteName
0x140114e98  call    cs:__imp_?MsoFRegReadWz@@YAHPEBU_msoreg@@PEA_WK@Z; MsoFRegReadWz(_msoreg const *,wchar_t *,ulong)
0x140114e9e  test    eax, eax
0x140114ea0  jz      short loc_140114EB3
0x140114ea2  lea     rcx, [rbp+1270h+var_10F0]
0x140114ea9  call    cs:__imp_??BCWzInBuffer@Jot@@QEAAPEA_WXZ; Jot::CWzInBuffer::operator wchar_t *(void)
0x140114eaf  mov     qword ptr [rbp+1270h+var_12D4+0Ch], rax
0x140114eb3  mov     rax, [rdi]
0x140114eb6  lea     rdx, [rsp+1370h+var_1310]
0x140114ebb  mov     rcx, rdi
0x140114ebe  mov     rax, [rax+10h]
0x140114ec2  call    cs:__guard_dispatch_icall_fptr
0x140114ec8  mov     rcx, rax
0x140114ecb  mov     [rsi+68h], rax
0x140114ecf  test    rax, rax
0x140114ed2  jnz     short loc_140114EE2
0x140114ed4  xor     edx, edx
0x140114ed6  mov     ecx, 1E42339Ch
0x140114edb  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x140114ee1  int     3; Trap to Debugger
0x140114ee2  mov     rax, [rax]
0x140114ee5  mov     rax, [rax+78h]
0x140114ee9  call    cs:__guard_dispatch_icall_fptr
0x140114eef  mov     rcx, rax; hWnd
0x140114ef2  mov     edi, 0FFFFFFF0h
0x140114ef7  mov     edx, edi; nIndex
0x140114ef9  call    cs:__imp_GetWindowLongW
0x140114eff  mov     ebx, eax
0x140114f01  and     ebx, 0FF30FFFFh
0x140114f07  mov     rcx, [rsi+68h]
0x140114f0b  mov     rax, [rcx]
0x140114f0e  mov     rax, [rax+78h]
0x140114f12  call    cs:__guard_dispatch_icall_fptr
0x140114f18  mov     rcx, rax; hWnd
0x140114f1b  mov     r8d, ebx; dwNewLong
0x140114f1e  mov     edx, edi; nIndex
0x140114f20  call    cs:__imp_SetWindowLongW
0x140114f26  mov     rcx, [rsi+68h]
0x140114f2a  mov     rax, [rcx]
0x140114f2d  mov     rdx, r14
0x140114f30  mov     rax, [rax+60h]
0x140114f34  call    cs:__guard_dispatch_icall_fptr
0x140114f3a  mov     rcx, [rsi+68h]
0x140114f3e  mov     rax, [rcx]
0x140114f41  mov     rdx, rsi
0x140114f44  mov     rax, [rax+88h]
0x140114f4b  call    cs:__guard_dispatch_icall_fptr
0x140114f51  mov     rax, cs:?s_pSingletonJotApp@CJotApp@Jot@@0PEAV12@EA; Jot::CJotApp * Jot::CJotApp::s_pSingletonJotApp
0x140114f58  mov     rdx, [rax+110h]
0x140114f5f  mov     rax, [rsi]
0x140114f62  mov     rcx, rsi
0x140114f65  mov     rax, [rax+90h]
0x140114f6c  call    cs:__guard_dispatch_icall_fptr
0x140114f72  mov     rcx, [rsi+68h]
0x140114f76  mov     rax, [rcx]
0x140114f79  mov     rax, [rax]
0x140114f7c  call    cs:__guard_dispatch_icall_fptr
0x140114f82  mov     rcx, rax
0x140114f85  mov     rax, [rax]
0x140114f88  mov     r8b, 1
0x140114f8b  mov     rdx, rsi
0x140114f8e  mov     rax, [rax+10h]
0x140114f92  call    cs:__guard_dispatch_icall_fptr
0x140114f98  mov     rax, [r12]
0x140114f9c  mov     rbx, [rax+8]
0x140114fa0  call    cs:__imp_?GetEmpty@AWorkspaceDependencyFactory@Jot@@SAAEBU12@XZ; Jot::AWorkspaceDependencyFactory::GetEmpty(void)
0x140114fa6  xorps   xmm0, xmm0
0x140114fa9  movdqu  [rbp+1270h+var_1270], xmm0
0x140114fae  mov     [rsp+1370h+var_1340], rax
0x140114fb3  mov     [rsp+1370h+var_1348], r15
0x140114fb8  lea     rax, [rbp+1270h+var_1270]
0x140114fbc  mov     [rsp+1370h+var_1350], rax
0x140114fc1  mov     r9b, 1
0x140114fc4  mov     r8, rsi
0x140114fc7  lea     rdx, [rsp+1370h+var_1320]
0x140114fcc  mov     rcx, r12
0x140114fcf  mov     rax, rbx
0x140114fd2  call    cs:__guard_dispatch_icall_fptr
0x140114fd8  lea     r14, [rsi+70h]
0x140114fdc  mov     rdx, rax
0x140114fdf  mov     rcx, r14
0x140114fe2  call    ??$?4U?$default_delete@UAWorkspace@Jot@@@std@@$0A@@?$unique_ptr@UAWorkspace@Jot@@U?$default_delete@UAWorkspace@Jot@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<Jot::AWorkspace>::operator=<std::default_delete<Jot::AWorkspace>,0>(std::unique_ptr<Jot::AWorkspace> &&)
0x140114fe7  lea     rcx, [rsp+1370h+var_1320]
0x140114fec  call    ??1?$unique_ptr@UANavigationWindowElement@Jot@@U?$default_delete@UANavigationWindowElement@Jot@@@std@@@std@@QEAA@XZ; std::unique_ptr<Jot::ANavigationWindowElement>::~unique_ptr<Jot::ANavigationWindowElement>(void)
0x140114ff1  mov     rcx, [r14]
0x140114ff4  test    rcx, rcx
0x140114ff7  jnz     short loc_140115007
0x140114ff9  xor     edx, edx
0x140114ffb  mov     ecx, 1E42339Ah
0x140115000  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x140115006  int     3; Trap to Debugger
0x140115007  mov     [rsi+0A0h], rsi
0x14011500e  mov     rdi, [rsi+68h]
0x140115012  mov     rax, [rdi]
0x140115015  mov     rbx, [rax+30h]
0x140115019  mov     rax, [rcx]
0x14011501c  lea     rdx, [rsp+1370h+var_1320]
0x140115021  mov     rax, [rax+20h]
0x140115025  call    cs:__guard_dispatch_icall_fptr
0x14011502b  nop
0x14011502c  mov     rdx, [rax]
0x14011502f  mov     rcx, rdi
0x140115032  mov     rax, rbx
0x140115035  call    cs:__guard_dispatch_icall_fptr
0x14011503b  nop
0x14011503c  mov     rcx, [rsp+1370h+var_1320]
0x140115041  test    rcx, rcx
0x140115044  jz      short loc_140115053
0x140115046  mov     rax, [rcx]
0x140115049  mov     rax, [rax+10h]
0x14011504d  call    cs:__guard_dispatch_icall_fptr
0x140115053  mov     rcx, [r14]
0x140115056  mov     rax, [rcx]
0x140115059  lea     rdx, [rbp+1270h+var_12A8]
0x14011505d  mov     rax, [rax+10h]
0x140115061  call    cs:__guard_dispatch_icall_fptr
0x140115067  nop
0x140115068  mov     rcx, rax
0x14011506b  call    ?Get@?$LegacyFuture@I@Mso@@QEBAIXZ; Mso::LegacyFuture<uint>::Get(void)
0x140115070  nop
0x140115071  lea     rcx, [rbp+1270h+var_12A8]
0x140115075  call    ??1?$Future@X@FastIntegration@Jot@@QEAA@XZ; Jot::FastIntegration::Future<void>::~Future<void>(void)
0x14011507a  mov     rcx, rsi; this
0x14011507d  call    ?UpdateContainedHwnds@CTutorialFrame@Jot@@QEAAXXZ; Jot::CTutorialFrame::UpdateContainedHwnds(void)
0x140115082  xor     edx, edx
0x140115084  lea     rcx, [rsp+1370h+var_1328]
0x140115089  call    cs:__imp_?CreatePropertySet@MsoCF@@YA?AV?$CIPtr@UIPropertySet@MsoCF@@U12@@1@PEAUIPropertySet@1@@Z; MsoCF::CreatePropertySet(MsoCF::IPropertySet *)
0x14011508f  nop
0x140115090  mov     [rsp+1370h+var_1330], r13b
0x140115095  mov     rcx, [rsp+1370h+var_1328]
0x14011509a  mov     rax, [rcx]
0x14011509d  lea     r8, [rsp+1370h+var_1330]
0x1401150a2  mov     rdx, cs:__imp_?priPageTitleVisible@PropertySpace_JotMain@Jot@@3UPropertyInfo@MsoCF@@B; MsoCF::PropertyInfo const Jot::PropertySpace_JotMain::priPageTitleVisible
0x1401150a9  mov     rax, [rax+38h]
0x1401150ad  call    cs:__guard_dispatch_icall_fptr
0x1401150b3  mov     rcx, [rsi+68h]
0x1401150b7  mov     rax, [rcx]
0x1401150ba  mov     r9d, 1
0x1401150c0  mov     r8, [rsp+1370h+var_1328]
0x1401150c5  mov     edx, 20293h
0x1401150ca  mov     rax, [rax+40h]
0x1401150ce  call    cs:__guard_dispatch_icall_fptr
0x1401150d4  mov     rcx, [r14]
0x1401150d7  test    rcx, rcx
0x1401150da  jz      short loc_1401150F1
0x1401150dc  mov     rax, [rcx]
0x1401150df  mov     rax, [rax+0A0h]
0x1401150e6  call    cs:__guard_dispatch_icall_fptr
0x1401150ec  mov     rcx, rax
0x1401150ef  jmp     short loc_1401150F4
0x1401150f1  mov     rcx, r13
0x1401150f4  test    rcx, rcx
0x1401150f7  jz      short loc_14011510B
0x1401150f9  mov     rax, [rcx]
0x1401150fc  mov     rax, [rax+8]
0x140115100  call    cs:__guard_dispatch_icall_fptr
0x140115106  mov     rcx, rax
0x140115109  jmp     short loc_14011510E
0x14011510b  mov     rcx, r13
0x14011510e  test    rcx, rcx
0x140115111  jz      short loc_140115128
0x140115113  mov     rax, [rcx]
0x140115116  mov     rax, [rax+190h]
0x14011511d  call    cs:__guard_dispatch_icall_fptr
0x140115123  mov     rcx, rax
0x140115126  jmp     short loc_14011512B
0x140115128  mov     rcx, r13
0x14011512b  test    rcx, rcx
0x14011512e  jz      short loc_140115142
0x140115130  mov     rax, [rcx]
0x140115133  mov     dl, 1
0x140115135  mov     rax, [rax+0C8h]
0x14011513c  call    cs:__guard_dispatch_icall_fptr
0x140115142  mov     rcx, [r14]
0x140115145  mov     rax, [rcx]
0x140115148  mov     rax, [rax+290h]
0x14011514f  call    cs:__guard_dispatch_icall_fptr
0x140115155  lea     rcx, aWmJotMainthrea; "WM_JOT_MAINTHREAD_APC"
0x14011515c  call    cs:__imp_RegisterWindowMessageW
0x140115162  mov     cs:?WM_JOT_TUTORIAL_MAINTHREAD_APC@@3IA, eax; uint WM_JOT_TUTORIAL_MAINTHREAD_APC
0x140115168  mov     rcx, [rsi+68h]
0x14011516c  mov     rax, [rcx]
0x14011516f  mov     edx, 5
0x140115174  mov     rax, [rax+0B0h]
0x14011517b  call    cs:__guard_dispatch_icall_fptr
0x140115181  mov     rcx, [rsi+68h]
0x140115185  mov     rax, [rcx]
0x140115188  mov     rax, [rax+78h]
0x14011518c  call    cs:__guard_dispatch_icall_fptr
0x140115192  xorps   xmm0, xmm0
0x140115195  movups  xmmword ptr [rbp+1270h+Rect.left], xmm0
0x140115199  lea     rdx, [rbp+1270h+Rect]; lpRect
0x14011519d  mov     rcx, rax; hWnd
0x1401151a0  call    cs:__imp_GetWindowRect
0x1401151a6  mov     eax, [rbp+1270h+Rect.right]
0x1401151a9  sub     eax, [rbp+1270h+Rect.left]
0x1401151ac  mov     [rsi+13Ch], eax
0x1401151b2  mov     eax, [rbp+1270h+Rect.bottom]
0x1401151b5  sub     eax, [rbp+1270h+Rect.top]
0x1401151b8  mov     [rsi+140h], eax
0x1401151be  mov     rcx, [r14]
0x1401151c1  mov     rax, [rcx]
0x1401151c4  mov     rax, [rax+58h]
0x1401151c8  call    cs:__guard_dispatch_icall_fptr
0x1401151ce  nop
0x1401151cf  mov     rcx, [rsp+1370h+var_1328]
0x1401151d4  test    rcx, rcx
0x1401151d7  jz      short loc_1401151E7
0x1401151d9  mov     rdx, [rcx]
0x1401151dc  mov     rax, [rdx+10h]
0x1401151e0  call    cs:__guard_dispatch_icall_fptr
0x1401151e6  nop
0x1401151e7  lea     rcx, [rbp+1270h+var_10F0]
0x1401151ee  call    ??1?$CWzInBuffer_T@V?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CFastBuffer@_W$0ICF@@2@@MsoCF@@$0ICE@@Jot@@QEAA@XZ; Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>::~CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>(void)
0x1401151f3  lea     rcx, [rbp+1270h+var_1260]
0x1401151f7  call    ??1?$CWzInBuffer_T@V?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CFastBuffer@_W$0ICF@@2@@MsoCF@@$0ICE@@Jot@@QEAA@XZ; Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>::~CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>(void)
0x1401151fc  mov     rax, rsi
0x1401151ff  mov     rcx, [rbp+1270h+var_40]
0x140115206  xor     rcx, rsp; StackCookie
0x140115209  call    __security_check_cookie
0x14011520e  mov     rbx, [rsp+1370h+arg_18]
0x140115216  add     rsp, 1340h
0x14011521d  pop     r15
0x14011521f  pop     r14
0x140115221  pop     r13
  ... truncated ...
```
