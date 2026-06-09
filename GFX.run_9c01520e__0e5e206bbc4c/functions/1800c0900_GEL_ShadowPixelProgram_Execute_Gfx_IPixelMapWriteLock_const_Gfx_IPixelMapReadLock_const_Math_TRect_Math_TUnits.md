# GEL::ShadowPixelProgram::Execute(Gfx::IPixelMapWriteLock const &,Gfx::IPixelMapReadLock const &,Math::TRect<Math::TUnits<uint,Math::DevicePixels>> const &,Gfx::IAbortSignal const *)

- ea: `0x1800c0900`
- end: `0x1800c0a64`
- name: `?Execute@ShadowPixelProgram@GEL@@UEBAXAEBUIPixelMapWriteLock@Gfx@@AEBUIPixelMapReadLock@4@AEBU?$TRect@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@PEBUIAbortSignal@4@@Z`
- size: `356`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x1800578b0`
- `0x180057e70`
- `0x180060314`
- `0x1800bfd50`
- `0x1800c0900`
- `0x1800c0a64`
- `0x1800c0ad0`
- `0x1800c0c60`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800c09fa`
- `KERNEL32!GetCurrentThreadId` at `0x1800c09fa`
- `mso40uiWin32Client!__imp_?ApplyColorFilter@Blur@Graphics@Mso@@YAXAEAV?$TPixelMap@U?$TBGRA@E$00@ARC@@@ARC@@AEBU?$TBGRA@E$00@5@AEBV?$FunctorRef@$$A6A_NX_E@3@@Z` at `0x1800c09bc`
- `mso40uiWin32Client!__imp_?ApplyColorFilter@Blur@Graphics@Mso@@YAXAEAV?$TPixelMap@U?$TBGRA@E$00@ARC@@@ARC@@AEBU?$TBGRA@E$00@5@AEBV?$FunctorRef@$$A6A_NX_E@3@@Z` at `0x1800c09bc`
- `mso40uiWin32Client!__imp_?ApplyBlur@Blur@Graphics@Mso@@YAXAEBV?$TPixelMap@$$CBU?$TBGRA@E$00@ARC@@@ARC@@AEBV?$TPixelMap@U?$TBGRA@E$00@ARC@@@5@AEBU?$TVector2@V?$TUnits@NUDevicePixels@Math@@@Math@@@Math@@W4BlurType@123@AEBV?$FunctorRef@$$A6A_NX_E@3@@Z` at `0x1800c099e`
- `mso40uiWin32Client!__imp_?ApplyBlur@Blur@Graphics@Mso@@YAXAEBV?$TPixelMap@$$CBU?$TBGRA@E$00@ARC@@@ARC@@AEBV?$TPixelMap@U?$TBGRA@E$00@ARC@@@5@AEBU?$TVector2@V?$TUnits@NUDevicePixels@Math@@@Math@@@Math@@W4BlurType@123@AEBV?$FunctorRef@$$A6A_NX_E@3@@Z` at `0x1800c099e`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1800c095d`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1800c095d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GEL::ShadowPixelProgram::Execute(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 *a5)
{
  __int64 v7; // r9
  int v8; // ebx
  bool v9; // al
  double *v10; // r8
  __int64 v12; // [rsp+30h] [rbp-31h] BYREF
  _BYTE v13[24]; // [rsp+38h] [rbp-29h] BYREF
  __int64 v14; // [rsp+50h] [rbp-11h]
  int v15[6]; // [rsp+58h] [rbp-9h] BYREF
  __int64 v16; // [rsp+70h] [rbp+Fh]
  __int64 (__fastcall **v17)(); // [rsp+78h] [rbp+17h] BYREF
  __int64 *v18; // [rsp+80h] [rbp+1Fh]
  char v19; // [rsp+88h] [rbp+27h]
  DWORD CurrentThreadId; // [rsp+8Ch] [rbp+2Bh]

  Gfx::TPixelMapWriteLock<ARC::TBGRA<unsigned char,1>,0>::TPixelMapWriteLock<ARC::TBGRA<unsigned char,1>,0>(v13, a2, a4);
  Gfx::TPixelMapReadLock<ARC::TBGRA<unsigned char,1>,0>::TPixelMapReadLock<ARC::TBGRA<unsigned char,1>,0>(v15, a3);
  v8 = 0;
  if ( byte_180523F78 < 0 )
    v9 = Mso::AB::Optimized::ChangeGate::Evaluate((Mso::AB::Optimized::ChangeGate *)&byte_180523F78);
  else
    v9 = byte_180523F78 != 0;
  v10 = (double *)(a1 + 8);
  if ( v9 )
  {
    v12 = (__int64)a5;
    v17 = &off_1804CB518;
    v18 = &v12;
    LOBYTE(v7) = (*(_BYTE *)(a1 + 24) != 0) + 2;
    Mso::Graphics::Blur::ApplyBlur(v15, v13, v10, v7, &v17);
    v17 = &off_1804CB518;
    v18 = &v12;
    Mso::Graphics::Blur::ApplyColorFilter(v13, a1 + 25, &v17);
  }
  else
  {
    if ( *(_BYTE *)(a1 + 24) )
    {
      if ( *(_BYTE *)(a1 + 24) == 1 )
        GEL::AlphaBlur::Draw<GEL::BoxGaussian,GEL::SSEBoxBlur>((__int64)v13, (__int64)v15, v10, (__int64)a5);
    }
    else
    {
      GEL::AlphaBlur::Draw<GEL::Gaussian,GEL::SSEGaussianBlur>((__int64)v13, v15, v10, (__int64)a5);
    }
    v18 = a5;
    v19 = 0;
    CurrentThreadId = GetCurrentThreadId();
    if ( !a5 )
      v8 = 16;
    LODWORD(v17) = v8;
    GEL::ApplyColorFilter(v13, &v17, a1 + 25);
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 8LL))(v16);
  return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
}

```

## disassembly

```asm
0x1800c0900  mov     [rsp-8+arg_18], rbx
0x1800c0905  push    rbp
0x1800c0906  push    rsi
0x1800c0907  push    rdi
0x1800c0908  lea     rbp, [rsp-3Fh]
0x1800c090d  sub     rsp, 0A0h
0x1800c0914  mov     rax, cs:__security_cookie
0x1800c091b  xor     rax, rsp
0x1800c091e  mov     [rbp+4Fh+var_20], rax
0x1800c0922  mov     rbx, r8
0x1800c0925  mov     rsi, rcx
0x1800c0928  mov     rdi, [rbp+4Fh+arg_20]
0x1800c092c  mov     r8, r9
0x1800c092f  lea     rcx, [rbp+4Fh+var_78]
0x1800c0933  call    ??0?$TPixelMapWriteLock@U?$TBGRA@E$00@ARC@@$0A@@Gfx@@QEAA@AEBUIPixelMapWriteLock@1@AEBU?$TRect@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@@Z; Gfx::TPixelMapWriteLock<ARC::TBGRA<uchar,1>,0>::TPixelMapWriteLock<ARC::TBGRA<uchar,1>,0>(Gfx::IPixelMapWriteLock const &,Math::TRect<Math::TUnits<uint,Math::DevicePixels>> const &)
0x1800c0938  mov     rdx, rbx
0x1800c093b  lea     rcx, [rbp+4Fh+var_58]
0x1800c093f  nop
0x1800c0940  call    ??0?$TPixelMapReadLock@U?$TBGRA@E$00@ARC@@$0A@@Gfx@@QEAA@AEBUIPixelMapReadLock@1@@Z; Gfx::TPixelMapReadLock<ARC::TBGRA<uchar,1>,0>::TPixelMapReadLock<ARC::TBGRA<uchar,1>,0>(Gfx::IPixelMapReadLock const &)
0x1800c0945  mov     al, cs:byte_180523F78
0x1800c094b  xor     ebx, ebx
0x1800c094d  test    al, al
0x1800c094f  js      short loc_1800C0956
0x1800c0951  setnz   al
0x1800c0954  jmp     short loc_1800C0963
0x1800c0956  lea     rcx, byte_180523F78
0x1800c095d  call    cs:__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ; Mso::AB::Optimized::ChangeGate::Evaluate(void)
0x1800c0963  lea     r8, [rsi+8]
0x1800c0967  test    al, al
0x1800c0969  jz      short loc_1800C09C4
0x1800c096b  mov     [rbp+4Fh+var_80], rdi
0x1800c096f  lea     rdi, off_1804CB518
0x1800c0976  mov     [rbp+4Fh+var_38], rdi
0x1800c097a  lea     rax, [rbp+4Fh+var_80]
0x1800c097e  mov     [rbp+4Fh+var_30], rax
0x1800c0982  cmp     [rsi+18h], bl
0x1800c0985  setnz   r9b
0x1800c0989  add     r9b, 2
0x1800c098d  lea     rax, [rbp+4Fh+var_38]
0x1800c0991  mov     [rsp+0B0h+var_90], rax
0x1800c0996  lea     rdx, [rbp+4Fh+var_78]
0x1800c099a  lea     rcx, [rbp+4Fh+var_58]
0x1800c099e  call    cs:__imp_?ApplyBlur@Blur@Graphics@Mso@@YAXAEBV?$TPixelMap@$$CBU?$TBGRA@E$00@ARC@@@ARC@@AEBV?$TPixelMap@U?$TBGRA@E$00@ARC@@@5@AEBU?$TVector2@V?$TUnits@NUDevicePixels@Math@@@Math@@@Math@@W4BlurType@123@AEBV?$FunctorRef@$$A6A_NX_E@3@@Z
0x1800c09a4  mov     [rbp+4Fh+var_38], rdi
0x1800c09a8  lea     rax, [rbp+4Fh+var_80]
0x1800c09ac  mov     [rbp+4Fh+var_30], rax
0x1800c09b0  lea     rdx, [rsi+19h]
0x1800c09b4  lea     r8, [rbp+4Fh+var_38]
0x1800c09b8  lea     rcx, [rbp+4Fh+var_78]
0x1800c09bc  call    cs:__imp_?ApplyColorFilter@Blur@Graphics@Mso@@YAXAEAV?$TPixelMap@U?$TBGRA@E$00@ARC@@@ARC@@AEBU?$TBGRA@E$00@5@AEBV?$FunctorRef@$$A6A_NX_E@3@@Z
0x1800c09c2  jmp     short loc_1800C0A23
0x1800c09c4  movzx   ecx, byte ptr [rsi+18h]
0x1800c09c8  test    ecx, ecx
0x1800c09ca  jz      short loc_1800C09E3
0x1800c09cc  cmp     ecx, 1
0x1800c09cf  jnz     short loc_1800C09F3
0x1800c09d1  mov     r9, rdi
0x1800c09d4  lea     rdx, [rbp+4Fh+var_58]
0x1800c09d8  lea     rcx, [rbp+4Fh+var_78]
0x1800c09dc  call    ??$Draw@VBoxGaussian@GEL@@VSSEBoxBlur@2@@AlphaBlur@GEL@@SAXAEBV?$TPixelMap@UPixel32@ARC@@@ARC@@0AEBU?$TVector2@V?$TUnits@NUDevicePixels@Math@@@Math@@@Math@@PEBUIAbortSignal@Gfx@@@Z; GEL::AlphaBlur::Draw<GEL::BoxGaussian,GEL::SSEBoxBlur>(ARC::TPixelMap<ARC::Pixel32> const &,ARC::TPixelMap<ARC::Pixel32> const &,Math::TVector2<Math::TUnits<double,Math::DevicePixels>> const &,Gfx::IAbortSignal const *)
0x1800c09e1  jmp     short loc_1800C09F3
0x1800c09e3  mov     r9, rdi
0x1800c09e6  lea     rdx, [rbp+4Fh+var_58]
0x1800c09ea  lea     rcx, [rbp+4Fh+var_78]
0x1800c09ee  call    ??$Draw@VGaussian@GEL@@VSSEGaussianBlur@2@@AlphaBlur@GEL@@SAXAEBV?$TPixelMap@UPixel32@ARC@@@ARC@@0AEBU?$TVector2@V?$TUnits@NUDevicePixels@Math@@@Math@@@Math@@PEBUIAbortSignal@Gfx@@@Z; GEL::AlphaBlur::Draw<GEL::Gaussian,GEL::SSEGaussianBlur>(ARC::TPixelMap<ARC::Pixel32> const &,ARC::TPixelMap<ARC::Pixel32> const &,Math::TVector2<Math::TUnits<double,Math::DevicePixels>> const &,Gfx::IAbortSignal const *)
0x1800c09f3  mov     [rbp+4Fh+var_30], rdi
0x1800c09f7  mov     [rbp+4Fh+var_28], bl
0x1800c09fa  call    cs:__imp_GetCurrentThreadId
0x1800c0a00  mov     [rbp+4Fh+var_24], eax
0x1800c0a03  mov     eax, 10h
0x1800c0a08  test    rdi, rdi
0x1800c0a0b  cmovz   ebx, eax
0x1800c0a0e  mov     dword ptr [rbp+4Fh+var_38], ebx
0x1800c0a11  lea     r8, [rsi+19h]
0x1800c0a15  lea     rdx, [rbp+4Fh+var_38]
0x1800c0a19  lea     rcx, [rbp+4Fh+var_78]
0x1800c0a1d  call    ?ApplyColorFilter@GEL@@YAXAEAV?$TPixelMap@U?$TBGRA@E$00@ARC@@@ARC@@AEAVScanlineAborter@1@AEBU?$TBGRA@E$00@3@@Z; GEL::ApplyColorFilter(ARC::TPixelMap<ARC::TBGRA<uchar,1>> &,GEL::ScanlineAborter &,ARC::TBGRA<uchar,1> const &)
0x1800c0a22  nop
0x1800c0a23  mov     rcx, [rbp+4Fh+var_40]
0x1800c0a27  mov     rax, [rcx]
0x1800c0a2a  mov     rax, [rax+8]
0x1800c0a2e  call    cs:__guard_dispatch_icall_fptr
0x1800c0a34  mov     rcx, [rbp+4Fh+var_60]
0x1800c0a38  mov     rax, [rcx]
0x1800c0a3b  mov     rax, [rax+8]
0x1800c0a3f  call    cs:__guard_dispatch_icall_fptr
0x1800c0a45  mov     rcx, [rbp+4Fh+var_20]
0x1800c0a49  xor     rcx, rsp; StackCookie
0x1800c0a4c  call    __security_check_cookie
0x1800c0a51  mov     rbx, [rsp+0B0h+arg_18]
0x1800c0a59  add     rsp, 0A0h
0x1800c0a60  pop     rdi
0x1800c0a61  pop     rsi
0x1800c0a62  pop     rbp
0x1800c0a63  retn
```
