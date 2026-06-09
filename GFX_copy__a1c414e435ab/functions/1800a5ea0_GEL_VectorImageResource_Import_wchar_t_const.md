# GEL::VectorImageResource::Import(wchar_t const *)

- ea: `0x1800a5ea0`
- end: `0x1800a61fa`
- name: `?Import@VectorImageResource@GEL@@AEAA_NPEB_W@Z`
- size: `858`
- prototype: `bool __fastcall(GEL::VectorImageResource *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800a5bd0`

## callees

- `0x180056ee0`
- `0x1800573f0`
- `0x18005f898`
- `0x180064d9c`
- `0x1800a5ea0`
- `0x1800a6200`
- `0x1800a6228`
- `0x1800a6254`
- `0x1800a62c4`

## import_xrefs

- `KERNEL32!MulDiv` at `0x1800a5f6d`
- `KERNEL32!MulDiv` at `0x1800a5f84`
- `KERNEL32!MulDiv` at `0x1800a5f6d`
- `KERNEL32!MulDiv` at `0x1800a5f84`
- `MSO!__imp_?MsoPibFromWzOptions@@YAPEAUIMsoBlip@@PEB_WKPEAUMSOABORT@@0H@Z` at `0x1800a5f0f`
- `MSO!__imp_?MsoPibFromWzOptions@@YAPEAUIMsoBlip@@PEB_WKPEAUMSOABORT@@0H@Z` at `0x1800a5f0f`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800a5fe5`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800a609f`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800a5fe5`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800a609f`
- `Mso20Win32Client!__imp_?EndsWith@StringAscii@Mso@@SA_NPEB_WH0H@Z` at `0x1800a5ef1`
- `Mso20Win32Client!__imp_?EndsWith@StringAscii@Mso@@SA_NPEB_WH0H@Z` at `0x1800a5ef1`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z` at `0x1800a6116`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z` at `0x1800a6116`
- `GDI32!EnumMetaFile` at `0x1800a6052`
- `GDI32!EnumMetaFile` at `0x1800a6052`
- `gdiplus!GdipLoadImageFromStreamICM` at `0x1800a619c`
- `gdiplus!GdipLoadImageFromStreamICM` at `0x1800a619c`
- `gdiplus!GdipCreateMetafileFromEmf` at `0x1800a612a`
- `gdiplus!GdipCreateMetafileFromEmf` at `0x1800a612a`
- `gdiplus!GdipCreateMetafileFromWmf` at `0x1800a6142`
- `gdiplus!GdipCreateMetafileFromWmf` at `0x1800a6142`
- `gdiplus!GdipDisposeImage` at `0x1800a60e2`
- `gdiplus!GdipDisposeImage` at `0x1800a61d8`
- `gdiplus!GdipDisposeImage` at `0x1800a60e2`
- `gdiplus!GdipDisposeImage` at `0x1800a61d8`
- `USER32!ReleaseDC` at `0x1800a6153`
- `USER32!ReleaseDC` at `0x1800a6153`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall GEL::VectorImageResource::Import(GEL::VectorImageResource *this, const wchar_t *a2)
{
  __int64 v4; // rdx
  struct IMsoBlip *v5; // rax
  struct IMsoBlip *v6; // rbx
  __int16 v8; // di
  __int16 v9; // ax
  __int16 *v10; // rdx
  __int16 v11; // cx
  int i; // r8d
  __int16 v13; // ax
  __int64 v14; // rdi
  HWND v15; // rdx
  HWND *v16; // rax
  HWND v17; // r12
  HDC v18; // rsi
  __int64 v19; // rax
  __int64 v20; // r14
  int v21; // eax
  int ImageFromStreamICM; // r14d
  __int64 v23; // rsi
  __int64 v24; // rdi
  unsigned int v25; // eax
  __int64 v26; // rax
  LPARAM param; // [rsp+30h] [rbp-40h] BYREF
  __int64 v28; // [rsp+38h] [rbp-38h] BYREF
  int nNumber[4]; // [rsp+40h] [rbp-30h] BYREF
  _DWORD v30[2]; // [rsp+50h] [rbp-20h] BYREF
  __int16 v31; // [rsp+58h] [rbp-18h]
  __int16 v32; // [rsp+5Ah] [rbp-16h]
  __int16 v33; // [rsp+5Ch] [rbp-14h]
  __int16 v34; // [rsp+5Eh] [rbp-12h]
  int v35; // [rsp+60h] [rbp-10h]
  __int16 v36; // [rsp+64h] [rbp-Ch]

  if ( !a2 )
    return 0;
  v4 = -1;
  do
    ++v4;
  while ( a2[v4] );
  if ( Mso::StringAscii::EndsWith(a2, v4, L".eps", 4) )
    Mso::Logging::MsoSendStructuredTraceTag(18638619, 144, 50, L"EPSFilterInsert");
  v5 = MsoPibFromWzOptions(a2, 0, 0, 0, 0);
  v6 = v5;
  if ( !v5 )
    return 0;
  while ( 1 )
  {
    (*(void (__fastcall **)(struct IMsoBlip *))(*(_QWORD *)v5 + 8LL))(v6);
    v14 = (*(__int64 (__fastcall **)(struct IMsoBlip *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v6 + 192LL))(v6, 0, 0, 0);
    ARC::GDIPlus::TGDIHolder<HMETAFILE__ *>::Empty((char *)this + 32);
    *((_QWORD *)this + 4) = v14;
    LOBYTE(param) = 0;
    v28 = 0;
    v16 = (HWND *)ARC::GDIPlus::HDCHwndPair::HDCHwndPair((ARC::GDIPlus::HDCHwndPair *)nNumber, v15);
    v17 = *v16;
    v18 = (HDC)v16[1];
    EnumMetaFile(v18, *((HMETAFILE *)this + 4), GEL::AnalyzeMetafileForEPS, (LPARAM)&param);
    v19 = *(_QWORD *)v6;
    if ( !(_BYTE)param )
      break;
    *(_QWORD *)nNumber = 0;
    (*(void (__fastcall **)(struct IMsoBlip *, int *))(v19 + 208))(v6, nNumber);
    v8 = MulDiv(nNumber[0], 96, 914400);
    v9 = MulDiv(nNumber[1], 96, 914400);
    v30[1] = 0;
    v35 = 0;
    v36 = 0;
    v30[0] = -1698247209;
    v31 = 0;
    v32 = v8;
    v33 = v9;
    v34 = 96;
    v10 = (__int16 *)v30 + 1;
    v11 = -12841;
    for ( i = 9; i > 0; --i )
    {
      v13 = *v10++;
      v11 ^= v13;
    }
    v36 = v11;
    if ( !v28 )
    {
      v21 = GdipCreateMetafileFromWmf(*((_QWORD *)this + 4), 0, v30, &v28);
      goto LABEL_15;
    }
    CrashWithRecovery(0x1E55E058u, 0);
  }
  v20 = (*(__int64 (__fastcall **)(struct IMsoBlip *, HDC, _QWORD, _QWORD))(v19 + 200))(v6, v18, 0, 0);
  ARC::GDIPlus::TGDIHolder<HENHMETAFILE__ *>::Empty((char *)this + 24);
  *((_QWORD *)this + 3) = v20;
  if ( v28 )
    CrashWithRecovery(0x1E55E058u, 0);
  else
    v21 = GdipCreateMetafileFromEmf(v20, 0, &v28);
LABEL_15:
  ImageFromStreamICM = v21;
  if ( v18 )
    ReleaseDC(v17, v18);
  if ( ImageFromStreamICM )
  {
    *(_QWORD *)nNumber = 0;
    v24 = *(_QWORD *)v6;
    v25 = (*(__int64 (__fastcall **)(struct IMsoBlip *))(*(_QWORD *)v6 + 48LL))(v6);
    if ( (*(unsigned int (__fastcall **)(struct IMsoBlip *, _QWORD, int *))(v24 + 288))(v6, v25, nNumber) )
    {
      v26 = ARC::GDIPlus::TGpHolder<Gdiplus::Matrix>::operator&((char *)this + 8);
      ImageFromStreamICM = GdipLoadImageFromStreamICM(*(_QWORD *)nNumber, v26);
    }
    if ( *(_QWORD *)nNumber )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)nNumber + 16LL))(*(_QWORD *)nNumber);
  }
  else
  {
    v23 = v28;
    v28 = 0;
    ARC::GDIPlus::TGpHolder<Gdiplus::GpBitmap>::Empty((char *)this + 8);
    *((_QWORD *)this + 1) = v23;
  }
  if ( ImageFromStreamICM )
  {
    if ( v28 )
    {
      GdipDisposeImage();
      v28 = 0;
    }
    (*(void (__fastcall **)(struct IMsoBlip *))(*(_QWORD *)v6 + 16LL))(v6);
    return 0;
  }
  Ofc::TCntPtr<ID2D1Effect>::Assign((char *)this + 16, 0);
  if ( v28 )
  {
    GdipDisposeImage();
    v28 = 0;
  }
  (*(void (__fastcall **)(struct IMsoBlip *))(*(_QWORD *)v6 + 16LL))(v6);
  return 1;
}

```

## disassembly

```asm
0x1800a5ea0  mov     [rsp-38h+arg_10], rbx
0x1800a5ea5  push    rbp
0x1800a5ea6  push    rsi
0x1800a5ea7  push    rdi
0x1800a5ea8  push    r12
0x1800a5eaa  push    r13
0x1800a5eac  push    r14
0x1800a5eae  push    r15
0x1800a5eb0  mov     rbp, rsp
0x1800a5eb3  sub     rsp, 70h
0x1800a5eb7  mov     rax, cs:__security_cookie
0x1800a5ebe  xor     rax, rsp
0x1800a5ec1  mov     [rbp+var_8], rax
0x1800a5ec5  mov     rbx, rdx
0x1800a5ec8  mov     r15, rcx
0x1800a5ecb  xor     r13d, r13d
0x1800a5ece  test    rdx, rdx
0x1800a5ed1  jz      short loc_1800A5F21
0x1800a5ed3  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800a5ed7  inc     rdx
0x1800a5eda  cmp     [rbx+rdx*2], r13w
0x1800a5edf  jnz     short loc_1800A5ED7
0x1800a5ee1  mov     r9d, 4
0x1800a5ee7  lea     r8, aEps; ".eps"
0x1800a5eee  mov     rcx, rbx
0x1800a5ef1  call    cs:__imp_?EndsWith@StringAscii@Mso@@SA_NPEB_WH0H@Z; Mso::StringAscii::EndsWith(wchar_t const *,int,wchar_t const *,int)
0x1800a5ef7  test    al, al
0x1800a5ef9  jnz     loc_1800A6101
0x1800a5eff  mov     [rsp+70h+var_50], r13d
0x1800a5f04  xor     r9d, r9d
0x1800a5f07  xor     r8d, r8d
0x1800a5f0a  xor     edx, edx
0x1800a5f0c  mov     rcx, rbx
0x1800a5f0f  call    cs:__imp_?MsoPibFromWzOptions@@YAPEAUIMsoBlip@@PEB_WKPEAUMSOABORT@@0H@Z; MsoPibFromWzOptions(wchar_t const *,ulong,MSOABORT *,wchar_t const *,int)
0x1800a5f15  mov     rbx, rax
0x1800a5f18  test    rax, rax
0x1800a5f1b  jnz     loc_1800A5FEC
0x1800a5f21  xor     al, al
0x1800a5f23  mov     rcx, [rbp+var_8]
0x1800a5f27  xor     rcx, rsp; StackCookie
0x1800a5f2a  call    __security_check_cookie
0x1800a5f2f  mov     rbx, [rsp+70h+arg_10]
0x1800a5f37  add     rsp, 70h
0x1800a5f3b  pop     r15
0x1800a5f3d  pop     r14
0x1800a5f3f  pop     r13
0x1800a5f41  pop     r12
0x1800a5f43  pop     rdi
0x1800a5f44  pop     rsi
0x1800a5f45  pop     rbp
0x1800a5f46  retn
0x1800a5f47  mov     qword ptr [rbp+nNumber], r13
0x1800a5f4b  lea     rdx, [rbp+nNumber]
0x1800a5f4f  mov     rax, [rax+0D0h]
0x1800a5f56  call    cs:__guard_dispatch_icall_fptr
0x1800a5f5c  mov     r13d, 0DF3E0h
0x1800a5f62  mov     r8d, r13d; nDenominator
0x1800a5f65  mov     edx, 60h ; '`'; nNumerator
0x1800a5f6a  mov     ecx, [rbp+nNumber]; nNumber
0x1800a5f6d  call    cs:__imp_MulDiv
0x1800a5f73  mov     edi, eax
0x1800a5f75  mov     r8d, r13d; nDenominator
0x1800a5f78  mov     r13d, 60h ; '`'
0x1800a5f7e  mov     edx, r13d; nNumerator
0x1800a5f81  mov     ecx, [rbp+nNumber+4]; nNumber
0x1800a5f84  call    cs:__imp_MulDiv
0x1800a5f8a  xor     ecx, ecx
0x1800a5f8c  mov     [rbp+var_1C], ecx
0x1800a5f8f  mov     [rbp+var_10], ecx
0x1800a5f92  mov     [rbp+var_C], cx
0x1800a5f96  mov     [rbp+var_20], 9AC6CDD7h
0x1800a5f9d  mov     [rbp+var_18], cx
0x1800a5fa1  mov     [rbp+var_16], di
0x1800a5fa5  mov     [rbp+var_14], ax
0x1800a5fa9  mov     [rbp+var_12], r13w
0x1800a5fae  lea     rdx, [rbp+var_20+2]
0x1800a5fb2  mov     ecx, 0FFFFCDD7h
0x1800a5fb7  lea     r8d, [r13-57h]
0x1800a5fbb  xor     r13d, r13d
0x1800a5fbe  movzx   eax, word ptr [rdx]
0x1800a5fc1  lea     rdx, [rdx+2]
0x1800a5fc5  xor     cx, ax
0x1800a5fc8  dec     r8d
0x1800a5fcb  test    r8d, r8d
0x1800a5fce  jg      short loc_1800A5FBE
0x1800a5fd0  mov     [rbp+var_C], cx
0x1800a5fd4  cmp     [rbp+var_38], r13
0x1800a5fd8  jz      loc_1800A6135
0x1800a5fde  xor     edx, edx
0x1800a5fe0  mov     ecx, 1E55E058h
0x1800a5fe5  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800a5feb  nop
0x1800a5fec  mov     rax, [rax]
0x1800a5fef  mov     rcx, rbx
0x1800a5ff2  mov     rax, [rax+8]
0x1800a5ff6  call    cs:__guard_dispatch_icall_fptr
0x1800a5ffc  lea     r14, [r15+20h]
0x1800a6000  mov     rax, [rbx]
0x1800a6003  xor     r9d, r9d
0x1800a6006  xor     r8d, r8d
0x1800a6009  xor     edx, edx
0x1800a600b  mov     rcx, rbx
0x1800a600e  mov     rax, [rax+0C0h]
0x1800a6015  call    cs:__guard_dispatch_icall_fptr
0x1800a601b  mov     rdi, rax
0x1800a601e  mov     rcx, r14
0x1800a6021  call    ?Empty@?$TGDIHolder@PEAUHMETAFILE__@@@GDIPlus@ARC@@QEAAXXZ; ARC::GDIPlus::TGDIHolder<HMETAFILE__ *>::Empty(void)
0x1800a6026  mov     [r14], rdi
0x1800a6029  mov     byte ptr [rbp+param], r13b
0x1800a602d  mov     [rbp+var_38], r13
0x1800a6031  lea     rcx, [rbp+nNumber]; this
0x1800a6035  call    ??0HDCHwndPair@GDIPlus@ARC@@QEAA@PEAUHWND__@@@Z; ARC::GDIPlus::HDCHwndPair::HDCHwndPair(HWND__ *)
0x1800a603a  mov     r12, [rax]
0x1800a603d  mov     rsi, [rax+8]
0x1800a6041  lea     r9, [rbp+param]; param
0x1800a6045  lea     r8, ?AnalyzeMetafileForEPS@GEL@@YAHPEAUHDC__@@PEAUtagHANDLETABLE@@PEAUtagMETARECORD@@H_J@Z; proc
0x1800a604c  mov     rdx, [r14]; hmf
0x1800a604f  mov     rcx, rsi; hdc
0x1800a6052  call    cs:__imp_EnumMetaFile
0x1800a6058  mov     rax, [rbx]
0x1800a605b  mov     rcx, rbx
0x1800a605e  cmp     byte ptr [rbp+param], r13b
0x1800a6062  jnz     loc_1800A5F47
0x1800a6068  xor     r9d, r9d
0x1800a606b  xor     r8d, r8d
0x1800a606e  mov     rdx, rsi
0x1800a6071  mov     rax, [rax+0C8h]
0x1800a6078  call    cs:__guard_dispatch_icall_fptr
0x1800a607e  mov     r14, rax
0x1800a6081  lea     rcx, [r15+18h]
0x1800a6085  call    ?Empty@?$TGDIHolder@PEAUHENHMETAFILE__@@@GDIPlus@ARC@@QEAAXXZ; ARC::GDIPlus::TGDIHolder<HENHMETAFILE__ *>::Empty(void)
0x1800a608a  mov     [r15+18h], r14
0x1800a608e  cmp     [rbp+var_38], r13
0x1800a6092  jz      loc_1800A6121
0x1800a6098  xor     edx, edx
0x1800a609a  mov     ecx, 1E55E058h
0x1800a609f  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800a60a5  nop
0x1800a60a6  mov     r14d, eax
0x1800a60a9  test    rsi, rsi
0x1800a60ac  jnz     loc_1800A614D
0x1800a60b2  test    r14d, r14d
0x1800a60b5  jnz     loc_1800A615E
0x1800a60bb  mov     rsi, [rbp+var_38]
0x1800a60bf  mov     [rbp+var_38], r13
0x1800a60c3  lea     rcx, [r15+8]
0x1800a60c7  call    ?Empty@?$TGpHolder@VGpBitmap@Gdiplus@@@GDIPlus@ARC@@QEAAXXZ; ARC::GDIPlus::TGpHolder<Gdiplus::GpBitmap>::Empty(void)
0x1800a60cc  mov     [r15+8], rsi
0x1800a60d0  test    r14d, r14d
0x1800a60d3  jz      loc_1800A61C4
0x1800a60d9  mov     rcx, [rbp+var_38]
0x1800a60dd  test    rcx, rcx
0x1800a60e0  jz      short loc_1800A60EC
0x1800a60e2  call    cs:__imp_GdipDisposeImage
0x1800a60e8  mov     [rbp+var_38], r13
0x1800a60ec  mov     rax, [rbx]
0x1800a60ef  mov     rcx, rbx
0x1800a60f2  mov     rax, [rax+10h]
0x1800a60f6  call    cs:__guard_dispatch_icall_fptr
0x1800a60fc  jmp     loc_1800A5F21
0x1800a6101  lea     r9, aEpsfilterinser; "EPSFilterInsert"
0x1800a6108  mov     edx, 90h
0x1800a610d  mov     ecx, 11C671Bh
0x1800a6112  lea     r8d, [rdx-5Eh]
0x1800a6116  call    cs:__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z; Mso::Logging::MsoSendStructuredTraceTag(ulong,Mso::Logging::Category,Mso::Logging::Severity,wchar_t const *)
0x1800a611c  jmp     loc_1800A5EFF
0x1800a6121  lea     r8, [rbp+var_38]
0x1800a6125  xor     edx, edx
0x1800a6127  mov     rcx, r14
0x1800a612a  call    cs:__imp_GdipCreateMetafileFromEmf
0x1800a6130  jmp     loc_1800A60A6
0x1800a6135  lea     r9, [rbp+var_38]
0x1800a6139  lea     r8, [rbp+var_20]
0x1800a613d  xor     edx, edx
0x1800a613f  mov     rcx, [r14]
0x1800a6142  call    cs:__imp_GdipCreateMetafileFromWmf
0x1800a6148  jmp     loc_1800A60A6
0x1800a614d  mov     rdx, rsi; hDC
0x1800a6150  mov     rcx, r12; hWnd
0x1800a6153  call    cs:__imp_ReleaseDC
0x1800a6159  jmp     loc_1800A60B2
0x1800a615e  mov     qword ptr [rbp+nNumber], r13
0x1800a6162  mov     rdi, [rbx]
0x1800a6165  mov     rcx, rbx
0x1800a6168  mov     rax, [rdi+30h]
0x1800a616c  call    cs:__guard_dispatch_icall_fptr
0x1800a6172  lea     r8, [rbp+nNumber]
0x1800a6176  mov     edx, eax
0x1800a6178  mov     rcx, rbx
0x1800a617b  mov     rax, [rdi+120h]
0x1800a6182  call    cs:__guard_dispatch_icall_fptr
0x1800a6188  test    eax, eax
0x1800a618a  jz      short loc_1800A61A5
0x1800a618c  lea     rcx, [r15+8]
0x1800a6190  call    ??I?$TGpHolder@VMatrix@Gdiplus@@@GDIPlus@ARC@@QEAAPEAPEAVMatrix@Gdiplus@@XZ; ARC::GDIPlus::TGpHolder<Gdiplus::Matrix>::operator&(void)
0x1800a6195  mov     rdx, rax
0x1800a6198  mov     rcx, qword ptr [rbp+nNumber]
0x1800a619c  call    cs:__imp_GdipLoadImageFromStreamICM
0x1800a61a2  mov     r14d, eax
0x1800a61a5  mov     rcx, qword ptr [rbp+nNumber]
0x1800a61a9  test    rcx, rcx
0x1800a61ac  jz      loc_1800A60D0
0x1800a61b2  mov     rax, [rcx]
0x1800a61b5  mov     rax, [rax+10h]
0x1800a61b9  call    cs:__guard_dispatch_icall_fptr
0x1800a61bf  jmp     loc_1800A60D0
0x1800a61c4  lea     rcx, [r15+10h]
0x1800a61c8  xor     edx, edx
0x1800a61ca  call    ?Assign@?$TCntPtr@UID2D1Effect@@@Ofc@@AEAAXPEAUID2D1Effect@@@Z; Ofc::TCntPtr<ID2D1Effect>::Assign(ID2D1Effect *)
0x1800a61cf  mov     rcx, [rbp+var_38]
0x1800a61d3  test    rcx, rcx
0x1800a61d6  jz      short loc_1800A61E2
0x1800a61d8  call    cs:__imp_GdipDisposeImage
0x1800a61de  mov     [rbp+var_38], r13
0x1800a61e2  mov     rcx, [rbx]
0x1800a61e5  mov     rax, [rcx+10h]
0x1800a61e9  mov     rcx, rbx
0x1800a61ec  call    cs:__guard_dispatch_icall_fptr
0x1800a61f2  mov     al, 1
0x1800a61f4  jmp     loc_1800A5F23
```
