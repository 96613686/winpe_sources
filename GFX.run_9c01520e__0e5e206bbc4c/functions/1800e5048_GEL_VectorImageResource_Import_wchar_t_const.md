# GEL::VectorImageResource::Import(wchar_t const *)

- ea: `0x1800e5048`
- end: `0x1800e53ae`
- name: `?Import@VectorImageResource@GEL@@AEAA_NPEB_W@Z`
- size: `870`
- prototype: `bool __fastcall(GEL::VectorImageResource *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800e4d84`

## callees

- `0x1800578b0`
- `0x180057e70`
- `0x18007faf8`
- `0x180082aac`
- `0x1800e32a4`
- `0x1800e5048`
- `0x1800e53b0`
- `0x1800e6a58`
- `0x180120914`

## import_xrefs

- `KERNEL32!MulDiv` at `0x1800e5115`
- `KERNEL32!MulDiv` at `0x1800e512c`
- `KERNEL32!MulDiv` at `0x1800e5115`
- `KERNEL32!MulDiv` at `0x1800e512c`
- `MSO!__imp_?MsoPibFromWzOptions@@YAPEAUIMsoBlip@@PEB_WKPEAUMSOABORT@@0H@Z` at `0x1800e50b7`
- `MSO!__imp_?MsoPibFromWzOptions@@YAPEAUIMsoBlip@@PEB_WKPEAUMSOABORT@@0H@Z` at `0x1800e50b7`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800e518d`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800e5253`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800e518d`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800e5253`
- `Mso20Win32Client!__imp_?EndsWith@StringAscii@Mso@@SA_NPEB_WH0H@Z` at `0x1800e5099`
- `Mso20Win32Client!__imp_?EndsWith@StringAscii@Mso@@SA_NPEB_WH0H@Z` at `0x1800e5099`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z` at `0x1800e52ca`
- `Mso20Win32Client!__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z` at `0x1800e52ca`
- `GDI32!EnumMetaFile` at `0x1800e5206`
- `GDI32!EnumMetaFile` at `0x1800e5206`
- `gdiplus!GdipLoadImageFromStreamICM` at `0x1800e5350`
- `gdiplus!GdipLoadImageFromStreamICM` at `0x1800e5350`
- `gdiplus!GdipCreateMetafileFromEmf` at `0x1800e52de`
- `gdiplus!GdipCreateMetafileFromEmf` at `0x1800e52de`
- `gdiplus!GdipCreateMetafileFromWmf` at `0x1800e52f6`
- `gdiplus!GdipCreateMetafileFromWmf` at `0x1800e52f6`
- `gdiplus!GdipDisposeImage` at `0x1800e5296`
- `gdiplus!GdipDisposeImage` at `0x1800e538c`
- `gdiplus!GdipDisposeImage` at `0x1800e5296`
- `gdiplus!GdipDisposeImage` at `0x1800e538c`
- `USER32!ReleaseDC` at `0x1800e5307`
- `USER32!ReleaseDC` at `0x1800e5307`

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
0x1800e5048  mov     [rsp-38h+arg_10], rbx
0x1800e504d  push    rbp
0x1800e504e  push    rsi
0x1800e504f  push    rdi
0x1800e5050  push    r12
0x1800e5052  push    r13
0x1800e5054  push    r14
0x1800e5056  push    r15
0x1800e5058  mov     rbp, rsp
0x1800e505b  sub     rsp, 70h
0x1800e505f  mov     rax, cs:__security_cookie
0x1800e5066  xor     rax, rsp
0x1800e5069  mov     [rbp+var_8], rax
0x1800e506d  mov     rbx, rdx
0x1800e5070  mov     r15, rcx
0x1800e5073  xor     r13d, r13d
0x1800e5076  test    rdx, rdx
0x1800e5079  jz      short loc_1800E50C9
0x1800e507b  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800e507f  inc     rdx
0x1800e5082  cmp     [rbx+rdx*2], r13w
0x1800e5087  jnz     short loc_1800E507F
0x1800e5089  mov     r9d, 4
0x1800e508f  lea     r8, aEps; ".eps"
0x1800e5096  mov     rcx, rbx
0x1800e5099  call    cs:__imp_?EndsWith@StringAscii@Mso@@SA_NPEB_WH0H@Z; Mso::StringAscii::EndsWith(wchar_t const *,int,wchar_t const *,int)
0x1800e509f  test    al, al
0x1800e50a1  jnz     loc_1800E52B5
0x1800e50a7  mov     [rsp+70h+var_50], r13d
0x1800e50ac  xor     r9d, r9d
0x1800e50af  xor     r8d, r8d
0x1800e50b2  xor     edx, edx
0x1800e50b4  mov     rcx, rbx
0x1800e50b7  call    cs:__imp_?MsoPibFromWzOptions@@YAPEAUIMsoBlip@@PEB_WKPEAUMSOABORT@@0H@Z; MsoPibFromWzOptions(wchar_t const *,ulong,MSOABORT *,wchar_t const *,int)
0x1800e50bd  mov     rbx, rax
0x1800e50c0  test    rax, rax
0x1800e50c3  jnz     loc_1800E51A0
0x1800e50c9  xor     al, al
0x1800e50cb  mov     rcx, [rbp+var_8]
0x1800e50cf  xor     rcx, rsp; StackCookie
0x1800e50d2  call    __security_check_cookie
0x1800e50d7  mov     rbx, [rsp+70h+arg_10]
0x1800e50df  add     rsp, 70h
0x1800e50e3  pop     r15
0x1800e50e5  pop     r14
0x1800e50e7  pop     r13
0x1800e50e9  pop     r12
0x1800e50eb  pop     rdi
0x1800e50ec  pop     rsi
0x1800e50ed  pop     rbp
0x1800e50ee  retn
0x1800e50ef  mov     qword ptr [rbp+nNumber], r13
0x1800e50f3  lea     rdx, [rbp+nNumber]
0x1800e50f7  mov     rax, [rax+0D0h]
0x1800e50fe  call    cs:__guard_dispatch_icall_fptr
0x1800e5104  mov     r13d, 0DF3E0h
0x1800e510a  mov     r8d, r13d; nDenominator
0x1800e510d  mov     edx, 60h ; '`'; nNumerator
0x1800e5112  mov     ecx, [rbp+nNumber]; nNumber
0x1800e5115  call    cs:__imp_MulDiv
0x1800e511b  mov     edi, eax
0x1800e511d  mov     r8d, r13d; nDenominator
0x1800e5120  mov     r13d, 60h ; '`'
0x1800e5126  mov     edx, r13d; nNumerator
0x1800e5129  mov     ecx, [rbp+nNumber+4]; nNumber
0x1800e512c  call    cs:__imp_MulDiv
0x1800e5132  xor     ecx, ecx
0x1800e5134  mov     [rbp+var_1C], ecx
0x1800e5137  mov     [rbp+var_10], ecx
0x1800e513a  mov     [rbp+var_C], cx
0x1800e513e  mov     [rbp+var_20], 9AC6CDD7h
0x1800e5145  mov     [rbp+var_18], cx
0x1800e5149  mov     [rbp+var_16], di
0x1800e514d  mov     [rbp+var_14], ax
0x1800e5151  mov     [rbp+var_12], r13w
0x1800e5156  lea     rdx, [rbp+var_20+2]
0x1800e515a  mov     ecx, 0FFFFCDD7h
0x1800e515f  lea     r8d, [r13-57h]
0x1800e5163  xor     r13d, r13d
0x1800e5166  movzx   eax, word ptr [rdx]
0x1800e5169  lea     rdx, [rdx+2]
0x1800e516d  xor     cx, ax
0x1800e5170  dec     r8d
0x1800e5173  test    r8d, r8d
0x1800e5176  jg      short loc_1800E5166
0x1800e5178  mov     [rbp+var_C], cx
0x1800e517c  cmp     [rbp+var_38], r13
0x1800e5180  jz      loc_1800E52E9
0x1800e5186  xor     edx, edx
0x1800e5188  mov     ecx, 1E55E058h
0x1800e518d  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800e5193  nop
0x1800e5194  nop     dword ptr [rax+00h]
0x1800e5198  nop     dword ptr [rax+rax+00000000h]
0x1800e51a0  mov     rax, [rax]
0x1800e51a3  mov     rcx, rbx
0x1800e51a6  mov     rax, [rax+8]
0x1800e51aa  call    cs:__guard_dispatch_icall_fptr
0x1800e51b0  lea     r14, [r15+20h]
0x1800e51b4  mov     rax, [rbx]
0x1800e51b7  xor     r9d, r9d
0x1800e51ba  xor     r8d, r8d
0x1800e51bd  xor     edx, edx
0x1800e51bf  mov     rcx, rbx
0x1800e51c2  mov     rax, [rax+0C0h]
0x1800e51c9  call    cs:__guard_dispatch_icall_fptr
0x1800e51cf  mov     rdi, rax
0x1800e51d2  mov     rcx, r14
0x1800e51d5  call    ?Empty@?$TGDIHolder@PEAUHMETAFILE__@@@GDIPlus@ARC@@QEAAXXZ; ARC::GDIPlus::TGDIHolder<HMETAFILE__ *>::Empty(void)
0x1800e51da  mov     [r14], rdi
0x1800e51dd  mov     byte ptr [rbp+param], r13b
0x1800e51e1  mov     [rbp+var_38], r13
0x1800e51e5  lea     rcx, [rbp+nNumber]; this
0x1800e51e9  call    ??0HDCHwndPair@GDIPlus@ARC@@QEAA@PEAUHWND__@@@Z; ARC::GDIPlus::HDCHwndPair::HDCHwndPair(HWND__ *)
0x1800e51ee  mov     r12, [rax]
0x1800e51f1  mov     rsi, [rax+8]
0x1800e51f5  lea     r9, [rbp+param]; param
0x1800e51f9  lea     r8, ?AnalyzeMetafileForEPS@GEL@@YAHPEAUHDC__@@PEAUtagHANDLETABLE@@PEAUtagMETARECORD@@H_J@Z; proc
0x1800e5200  mov     rdx, [r14]; hmf
0x1800e5203  mov     rcx, rsi; hdc
0x1800e5206  call    cs:__imp_EnumMetaFile
0x1800e520c  mov     rax, [rbx]
0x1800e520f  mov     rcx, rbx
0x1800e5212  cmp     byte ptr [rbp+param], r13b
0x1800e5216  jnz     loc_1800E50EF
0x1800e521c  xor     r9d, r9d
0x1800e521f  xor     r8d, r8d
0x1800e5222  mov     rdx, rsi
0x1800e5225  mov     rax, [rax+0C8h]
0x1800e522c  call    cs:__guard_dispatch_icall_fptr
0x1800e5232  mov     r14, rax
0x1800e5235  lea     rcx, [r15+18h]
0x1800e5239  call    ?Empty@?$TGDIHolder@PEAUHENHMETAFILE__@@@GDIPlus@ARC@@QEAAXXZ; ARC::GDIPlus::TGDIHolder<HENHMETAFILE__ *>::Empty(void)
0x1800e523e  mov     [r15+18h], r14
0x1800e5242  cmp     [rbp+var_38], r13
0x1800e5246  jz      loc_1800E52D5
0x1800e524c  xor     edx, edx
0x1800e524e  mov     ecx, 1E55E058h
0x1800e5253  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800e5259  nop
0x1800e525a  mov     r14d, eax
0x1800e525d  test    rsi, rsi
0x1800e5260  jnz     loc_1800E5301
0x1800e5266  test    r14d, r14d
0x1800e5269  jnz     loc_1800E5312
0x1800e526f  mov     rsi, [rbp+var_38]
0x1800e5273  mov     [rbp+var_38], r13
0x1800e5277  lea     rcx, [r15+8]
0x1800e527b  call    ?Empty@?$TGpHolder@VGpBitmap@Gdiplus@@@GDIPlus@ARC@@QEAAXXZ; ARC::GDIPlus::TGpHolder<Gdiplus::GpBitmap>::Empty(void)
0x1800e5280  mov     [r15+8], rsi
0x1800e5284  test    r14d, r14d
0x1800e5287  jz      loc_1800E5378
0x1800e528d  mov     rcx, [rbp+var_38]
0x1800e5291  test    rcx, rcx
0x1800e5294  jz      short loc_1800E52A0
0x1800e5296  call    cs:__imp_GdipDisposeImage
0x1800e529c  mov     [rbp+var_38], r13
0x1800e52a0  mov     rax, [rbx]
0x1800e52a3  mov     rcx, rbx
0x1800e52a6  mov     rax, [rax+10h]
0x1800e52aa  call    cs:__guard_dispatch_icall_fptr
0x1800e52b0  jmp     loc_1800E50C9
0x1800e52b5  lea     r9, aEpsfilterinser; "EPSFilterInsert"
0x1800e52bc  mov     edx, 90h
0x1800e52c1  mov     ecx, 11C671Bh
0x1800e52c6  lea     r8d, [rdx-5Eh]
0x1800e52ca  call    cs:__imp_?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z; Mso::Logging::MsoSendStructuredTraceTag(ulong,Mso::Logging::Category,Mso::Logging::Severity,wchar_t const *)
0x1800e52d0  jmp     loc_1800E50A7
0x1800e52d5  lea     r8, [rbp+var_38]
0x1800e52d9  xor     edx, edx
0x1800e52db  mov     rcx, r14
0x1800e52de  call    cs:__imp_GdipCreateMetafileFromEmf
0x1800e52e4  jmp     loc_1800E525A
0x1800e52e9  lea     r9, [rbp+var_38]
0x1800e52ed  lea     r8, [rbp+var_20]
0x1800e52f1  xor     edx, edx
0x1800e52f3  mov     rcx, [r14]
0x1800e52f6  call    cs:__imp_GdipCreateMetafileFromWmf
0x1800e52fc  jmp     loc_1800E525A
0x1800e5301  mov     rdx, rsi; hDC
0x1800e5304  mov     rcx, r12; hWnd
0x1800e5307  call    cs:__imp_ReleaseDC
0x1800e530d  jmp     loc_1800E5266
0x1800e5312  mov     qword ptr [rbp+nNumber], r13
0x1800e5316  mov     rdi, [rbx]
0x1800e5319  mov     rcx, rbx
0x1800e531c  mov     rax, [rdi+30h]
0x1800e5320  call    cs:__guard_dispatch_icall_fptr
0x1800e5326  lea     r8, [rbp+nNumber]
0x1800e532a  mov     edx, eax
0x1800e532c  mov     rcx, rbx
0x1800e532f  mov     rax, [rdi+120h]
0x1800e5336  call    cs:__guard_dispatch_icall_fptr
0x1800e533c  test    eax, eax
0x1800e533e  jz      short loc_1800E5359
0x1800e5340  lea     rcx, [r15+8]
0x1800e5344  call    ??I?$TGpHolder@VMatrix@Gdiplus@@@GDIPlus@ARC@@QEAAPEAPEAVMatrix@Gdiplus@@XZ; ARC::GDIPlus::TGpHolder<Gdiplus::Matrix>::operator&(void)
0x1800e5349  mov     rdx, rax
0x1800e534c  mov     rcx, qword ptr [rbp+nNumber]
0x1800e5350  call    cs:__imp_GdipLoadImageFromStreamICM
0x1800e5356  mov     r14d, eax
0x1800e5359  mov     rcx, qword ptr [rbp+nNumber]
0x1800e535d  test    rcx, rcx
0x1800e5360  jz      loc_1800E5284
0x1800e5366  mov     rax, [rcx]
0x1800e5369  mov     rax, [rax+10h]
0x1800e536d  call    cs:__guard_dispatch_icall_fptr
0x1800e5373  jmp     loc_1800E5284
0x1800e5378  lea     rcx, [r15+10h]
0x1800e537c  xor     edx, edx
0x1800e537e  call    ?Assign@?$TCntPtr@UID2D1Effect@@@Ofc@@AEAAXPEAUID2D1Effect@@@Z; Ofc::TCntPtr<ID2D1Effect>::Assign(ID2D1Effect *)
0x1800e5383  mov     rcx, [rbp+var_38]
0x1800e5387  test    rcx, rcx
0x1800e538a  jz      short loc_1800E5396
0x1800e538c  call    cs:__imp_GdipDisposeImage
0x1800e5392  mov     [rbp+var_38], r13
0x1800e5396  mov     rcx, [rbx]
0x1800e5399  mov     rax, [rcx+10h]
0x1800e539d  mov     rcx, rbx
0x1800e53a0  call    cs:__guard_dispatch_icall_fptr
0x1800e53a6  mov     al, 1
0x1800e53a8  jmp     loc_1800E50CB
```
