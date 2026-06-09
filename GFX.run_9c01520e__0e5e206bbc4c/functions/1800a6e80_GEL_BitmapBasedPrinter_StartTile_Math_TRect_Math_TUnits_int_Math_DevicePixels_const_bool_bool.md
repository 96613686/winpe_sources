# GEL::BitmapBasedPrinter::StartTile(Math::TRect<Math::TUnits<int,Math::DevicePixels>> const &,bool,bool)

- ea: `0x1800a6e80`
- end: `0x1800a71c1`
- name: `?StartTile@BitmapBasedPrinter@GEL@@UEAA_NAEBU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@_N1@Z`
- size: `833`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: ``

## callees

- `0x18003e880`
- `0x180051d08`
- `0x1800578b0`
- `0x18007f754`
- `0x18007faf8`
- `0x180081440`
- `0x180082aac`
- `0x1800a4550`
- `0x1800a6848`
- `0x1800a6e80`
- `0x1800a7280`
- `0x1800a75bc`
- `0x1800dd460`
- `0x1800e34f0`

## import_xrefs

- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1800a6eec`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1800a6eec`
- `GDI32!CreateDIBSection` at `0x1800a70c9`
- `GDI32!CreateDIBSection` at `0x1800a70c9`
- `gdiplus!GdipCreateBitmapFromGdiDib` at `0x1800a712e`
- `gdiplus!GdipCreateBitmapFromGdiDib` at `0x1800a712e`

## pseudocode

```c
char __fastcall GEL::BitmapBasedPrinter::StartTile(__int64 a1, __int128 *a2, char a3, char a4)
{
  __int64 v10; // rax
  _DWORD *v11; // rax
  int v12; // edi
  int v13; // esi
  int v14; // r15d
  int v15; // ebx
  int v16; // ecx
  int v17; // eax
  int v18; // ecx
  int v19; // r15d
  int v20; // eax
  int v21; // ecx
  HBITMAP v22; // rbx
  int v23; // edx
  char v24; // r9
  __int64 v25; // rax
  unsigned int v26; // eax
  __int64 v27; // rdx
  __int64 v28; // r8
  __int128 v29; // [rsp+48h] [rbp-29h] BYREF
  int v30; // [rsp+58h] [rbp-19h]
  __int16 v31; // [rsp+5Ch] [rbp-15h]
  void *ppvBits[2]; // [rsp+60h] [rbp-11h] BYREF
  BITMAPINFO pbmi; // [rsp+70h] [rbp-1h] BYREF

  if ( !*(_BYTE *)(a1 + 449) )
    return 0;
  if ( *(_DWORD *)(a1 + 320) == 3
    && (byte_180524108 < 0
      ? Mso::AB::Optimized::FeatureGate::Evaluate((Mso::AB::Optimized::FeatureGate *)&byte_180524108)
      : byte_180524108 != 0) )
  {
    v30 = 3;
    *(_QWORD *)&v29 = &Mso::Logging::StructuredObject<unsigned int,1>::`vftable';
    v31 = 0;
    *((_QWORD *)&v29 + 1) = L"GdipStatus";
    OExceptionLog::ThrowTagVariableArguments<Mso::Logging::StructuredObject<unsigned int,1>>(
      557913748,
      (_DWORD)a2,
      3,
      a4);
  }
  v29 = *a2;
  if ( !GEL::Printer::StartTile(a1, &v29, a3, a4) )
    return 0;
  *(_BYTE *)(a1 + 586) = a3;
  if ( a3 )
  {
    *(_BYTE *)(a1 + 240) = 0;
    return 1;
  }
  else
  {
    GEL::BitmapBasedPrinter::GetScalingFactor(a1, &v29);
    *(double *)ppvBits = 1.0 / *(double *)&v29;
    *(double *)&ppvBits[1] = 1.0 / *((double *)&v29 + 1);
    v10 = Math::operator*<Math::TUnits<int,Math::DevicePixels>,double,Math::TUnits<double,Math::DevicePixels>>(
            &pbmi,
            a1 + 324,
            ppvBits);
    Math::snap_outward_cast<Math::TUnits<int,Math::DevicePixels>,Math::TUnits<double,Math::DevicePixels>,0,0>(&v29, v10);
    v11 = (_DWORD *)sub_1800A6848(ppvBits);
    v12 = v29;
    v13 = DWORD2(v29);
    v14 = HIDWORD(v29);
    v15 = DWORD1(v29);
    v16 = 2 * *v11;
    if ( (int)v29 > SDWORD2(v29) || SDWORD1(v29) > SHIDWORD(v29) )
      v17 = 0;
    else
      v17 = DWORD2(v29) - v29;
    *(_DWORD *)(a1 + 496) = v16 + v17;
    v18 = 2 * *(_DWORD *)sub_1800A6848(ppvBits);
    if ( v12 > v13 || v15 > v14 )
      v19 = 0;
    else
      v19 = v14 - v15;
    v20 = v18 + v19;
    v21 = *(_DWORD *)(a1 + 496);
    *(_DWORD *)(a1 + 500) = v20;
    if ( v21 < 0 || v20 < 0 )
    {
      GEL::FailureException::ThrowTag(0x8591DAu);
      __debugbreak();
    }
    if ( *(_QWORD *)(a1 + 480) && (v21 != *(_DWORD *)(a1 + 504) || v20 != *(_DWORD *)(a1 + 508)) )
      ARC::GDIPlus::TGpHolder<Gdiplus::GpBitmap>::Empty(a1 + 480);
    if ( !*(_QWORD *)(a1 + 480) )
    {
      pbmi.bmiHeader.biWidth = *(_DWORD *)(a1 + 496);
      pbmi.bmiHeader.biHeight = -*(_DWORD *)(a1 + 500);
      memset(&pbmi.bmiHeader.biSizeImage, 0, 24);
      pbmi.bmiHeader.biSize = 40;
      *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
      ppvBits[0] = 0;
      ARC::GDIPlus::TGDIHolder<HBITMAP__ *>::Empty(a1 + 472);
      v22 = CreateDIBSection(0, &pbmi, 0, ppvBits, 0, 0);
      ARC::GDIPlus::TGDIHolder<HBITMAP__ *>::Empty(a1 + 472);
      *(_QWORD *)(a1 + 472) = v22;
      if ( !ppvBits[0] )
      {
        v31 = 0;
        *(_QWORD *)&v29 = &Mso::Logging::StructuredObject<unsigned int,1>::`vftable';
        v30 = 3;
        *((_QWORD *)&v29 + 1) = L"GdipStatus";
        OExceptionLog::ThrowTagVariableArguments<Mso::Logging::StructuredObject<unsigned int,1>>(558458784, v23, 3, v24);
      }
      v25 = ARC::GDIPlus::TGpHolder<Gdiplus::Matrix>::operator&(a1 + 480);
      v26 = GdipCreateBitmapFromGdiDib(&pbmi, ppvBits[0], v25);
      Gfx::GdipStatus_ThrowOnFailureMessageTag(v26, v27, v28, 38869189);
    }
    *((_QWORD *)&v29 + 1) = *(_QWORD *)(a1 + 496);
    *(_QWORD *)&v29 = 0;
    GEL::BitmapBasedPrinter::WhiteOutBitmap((_QWORD *)(a1 + 480), (unsigned int *)&v29);
    *(_DWORD *)(a1 + 504) = *(_DWORD *)(a1 + 496);
    *(_DWORD *)(a1 + 508) = *(_DWORD *)(a1 + 500);
    return 1;
  }
}

```

## disassembly

```asm
0x1800a6e80  mov     rax, rsp
0x1800a6e83  mov     [rax+10h], rbx
0x1800a6e87  mov     [rax+18h], rsi
0x1800a6e8b  mov     [rax+20h], rdi
0x1800a6e8f  push    rbp
0x1800a6e90  push    r12
0x1800a6e92  push    r13
0x1800a6e94  push    r14
0x1800a6e96  push    r15
0x1800a6e98  lea     rbp, [rax-5Fh]
0x1800a6e9c  sub     rsp, 0A0h
0x1800a6ea3  mov     rax, cs:__security_cookie
0x1800a6eaa  xor     rax, rsp
0x1800a6ead  mov     [rbp+57h+var_28], rax
0x1800a6eb1  xor     r13d, r13d
0x1800a6eb4  mov     dil, r9b
0x1800a6eb7  mov     bl, r8b
0x1800a6eba  mov     rsi, rdx
0x1800a6ebd  mov     r14, rcx
0x1800a6ec0  cmp     [rcx+1C1h], r13b
0x1800a6ec7  jz      loc_1800A7192
0x1800a6ecd  cmp     dword ptr [rcx+140h], 3
0x1800a6ed4  jnz     short loc_1800A6F32
0x1800a6ed6  mov     al, cs:byte_180524108
0x1800a6edc  test    al, al
0x1800a6ede  js      short loc_1800A6EE5
0x1800a6ee0  setnz   al
0x1800a6ee3  jmp     short loc_1800A6EF2
0x1800a6ee5  lea     rcx, byte_180524108
0x1800a6eec  call    cs:__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ; Mso::AB::Optimized::FeatureGate::Evaluate(void)
0x1800a6ef2  test    al, al
0x1800a6ef4  jz      short loc_1800A6F32
0x1800a6ef6  lea     rax, ??_7?$StructuredObject@I$00@Logging@Mso@@6B@; const Mso::Logging::StructuredObject<uint,1>::`vftable'
0x1800a6efd  mov     [rbp+57h+var_70], 3
0x1800a6f04  mov     qword ptr [rbp+57h+var_80], rax
0x1800a6f08  mov     ecx, 21411694h
0x1800a6f0d  lea     rax, aGdipstatus; "GdipStatus"
0x1800a6f14  mov     [rbp+57h+var_6C], r13w
0x1800a6f19  mov     qword ptr [rbp+57h+var_80+8], rax
0x1800a6f1d  mov     r8d, 3
0x1800a6f23  lea     rax, [rbp+57h+var_80]
0x1800a6f27  mov     [rsp+0C0h+var_90], rax
0x1800a6f2c  call    ??$ThrowTagVariableArguments@U?$StructuredObject@I$00@Logging@Mso@@@OExceptionLog@@YAXKW4exceptionType@et@@JPEB_WW4Category@Logging@Mso@@W4Severity@45@$$QEAU?$StructuredObject@I$00@45@@Z; OExceptionLog::ThrowTagVariableArguments<Mso::Logging::StructuredObject<uint,1>>(ulong,et::exceptionType,long,wchar_t const *,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::StructuredObject<uint,1> &&)
0x1800a6f32  movups  xmm0, xmmword ptr [rsi]
0x1800a6f35  mov     r9b, dil
0x1800a6f38  lea     rdx, [rbp+57h+var_80]
0x1800a6f3c  mov     r8b, bl
0x1800a6f3f  mov     rcx, r14
0x1800a6f42  movdqu  [rbp+57h+var_80], xmm0
0x1800a6f47  call    ?StartTile@Printer@GEL@@UEAA_NAEBU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@_N1@Z; GEL::Printer::StartTile(Math::TRect<Math::TUnits<int,Math::DevicePixels>> const &,bool,bool)
0x1800a6f4c  test    al, al
0x1800a6f4e  jz      loc_1800A7192
0x1800a6f54  mov     [r14+24Ah], bl
0x1800a6f5b  test    bl, bl
0x1800a6f5d  jz      short loc_1800A6F70
0x1800a6f5f  mov     [r14+0F0h], r13b
0x1800a6f66  mov     eax, 1
0x1800a6f6b  jmp     loc_1800A7194
0x1800a6f70  lea     rdx, [rbp+57h+var_80]
0x1800a6f74  mov     rcx, r14
0x1800a6f77  call    ?GetScalingFactor@BitmapBasedPrinter@GEL@@UEBA?AU?$TScaling2@N@Math@@XZ; GEL::BitmapBasedPrinter::GetScalingFactor(void)
0x1800a6f7c  movsd   xmm1, cs:__real@3ff0000000000000
0x1800a6f84  lea     rdx, [r14+144h]
0x1800a6f8b  movaps  xmm0, xmm1
0x1800a6f8e  lea     r8, [rbp+57h+ppvBits]
0x1800a6f92  divsd   xmm0, qword ptr [rbp+57h+var_80]
0x1800a6f97  lea     rcx, [rbp+57h+pbmi]
0x1800a6f9b  divsd   xmm1, qword ptr [rbp+57h+var_80+8]
0x1800a6fa0  movsd   [rbp+57h+ppvBits], xmm0
0x1800a6fa5  movsd   [rbp+57h+var_60], xmm1
0x1800a6faa  call    ??$?DV?$TUnits@HUDevicePixels@Math@@@Math@@NV?$TUnits@NUDevicePixels@Math@@@1@@Math@@YA?AU?$TRect@V?$TUnits@NUDevicePixels@Math@@@Math@@@0@AEBU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@0@AEBU?$TScaling2@N@0@@Z; Math::operator*<Math::TUnits<int,Math::DevicePixels>,double,Math::TUnits<double,Math::DevicePixels>>(Math::TRect<Math::TUnits<int,Math::DevicePixels>> const &,Math::TScaling2<double> const &)
0x1800a6faf  mov     rdx, rax
0x1800a6fb2  lea     rcx, [rbp+57h+var_80]
0x1800a6fb6  call    ??$snap_outward_cast@V?$TUnits@HUDevicePixels@Math@@@Math@@V?$TUnits@NUDevicePixels@Math@@@2@$0A@$0A@@Math@@YA?AU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@0@AEBU?$TRect@V?$TUnits@NUDevicePixels@Math@@@Math@@@0@@Z; Math::snap_outward_cast<Math::TUnits<int,Math::DevicePixels>,Math::TUnits<double,Math::DevicePixels>,0,0>(Math::TRect<Math::TUnits<double,Math::DevicePixels>> const &)
0x1800a6fbb  lea     rcx, [rbp+57h+ppvBits]
0x1800a6fbf  call    sub_1800A6848
0x1800a6fc4  mov     edi, dword ptr [rbp+57h+var_80]
0x1800a6fc7  mov     esi, dword ptr [rbp+57h+var_80+8]
0x1800a6fca  mov     r15d, dword ptr [rbp+57h+var_80+0Ch]
0x1800a6fce  mov     ecx, [rax]
0x1800a6fd0  mov     ebx, dword ptr [rbp+57h+var_80+4]
0x1800a6fd3  add     ecx, ecx
0x1800a6fd5  cmp     edi, esi
0x1800a6fd7  jg      short loc_1800A6FE4
0x1800a6fd9  cmp     ebx, r15d
0x1800a6fdc  jg      short loc_1800A6FE4
0x1800a6fde  mov     eax, esi
0x1800a6fe0  sub     eax, edi
0x1800a6fe2  jmp     short loc_1800A6FE7
0x1800a6fe4  mov     eax, r13d
0x1800a6fe7  add     eax, ecx
0x1800a6fe9  lea     rcx, [rbp+57h+ppvBits]
0x1800a6fed  mov     [r14+1F0h], eax
0x1800a6ff4  call    sub_1800A6848
0x1800a6ff9  mov     ecx, [rax]
0x1800a6ffb  add     ecx, ecx
0x1800a6ffd  cmp     edi, esi
0x1800a6fff  jg      short loc_1800A700B
0x1800a7001  cmp     ebx, r15d
0x1800a7004  jg      short loc_1800A700B
0x1800a7006  sub     r15d, ebx
0x1800a7009  jmp     short loc_1800A700E
0x1800a700b  mov     r15d, r13d
0x1800a700e  lea     eax, [rcx+r15]
0x1800a7012  mov     ecx, [r14+1F0h]
0x1800a7019  mov     [r14+1F4h], eax
0x1800a7020  test    ecx, ecx
0x1800a7022  js      loc_1800A7187
0x1800a7028  test    eax, eax
0x1800a702a  js      loc_1800A7187
0x1800a7030  lea     r12, [r14+1E0h]
0x1800a7037  cmp     [r12], r13
0x1800a703b  jz      short loc_1800A7057
0x1800a703d  cmp     ecx, [r14+1F8h]
0x1800a7044  jnz     short loc_1800A704F
0x1800a7046  cmp     eax, [r14+1FCh]
0x1800a704d  jz      short loc_1800A7057
0x1800a704f  mov     rcx, r12
0x1800a7052  call    ?Empty@?$TGpHolder@VGpBitmap@Gdiplus@@@GDIPlus@ARC@@QEAAXXZ; ARC::GDIPlus::TGpHolder<Gdiplus::GpBitmap>::Empty(void)
0x1800a7057  xor     ebx, ebx
0x1800a7059  mov     r13, r14
0x1800a705c  mov     esi, 1F8h
0x1800a7061  lea     r15d, [rbx+1]
0x1800a7065  cmp     [r12], rbx
0x1800a7069  jnz     loc_1800A7141
0x1800a706f  mov     eax, [r14+1F0h]
0x1800a7076  lea     rdi, [r14+1D8h]
0x1800a707d  mov     [rbp+57h+pbmi.bmiHeader.biWidth], eax
0x1800a7080  xorps   xmm0, xmm0
0x1800a7083  mov     eax, [r14+1F4h]
0x1800a708a  mov     rcx, rdi
0x1800a708d  neg     eax
0x1800a708f  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biClrImportant], rbx
0x1800a7093  mov     [rbp+57h+pbmi.bmiHeader.biHeight], eax
0x1800a7096  movdqu  xmmword ptr [rbp+57h+pbmi.bmiHeader.biSizeImage], xmm0
0x1800a709b  mov     [rbp+57h+pbmi.bmiHeader.biSize], 28h ; '('
0x1800a70a2  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biPlanes], 200001h
0x1800a70aa  mov     [rbp+57h+ppvBits], rbx
0x1800a70ae  call    ?Empty@?$TGDIHolder@PEAUHBITMAP__@@@GDIPlus@ARC@@QEAAXXZ; ARC::GDIPlus::TGDIHolder<HBITMAP__ *>::Empty(void)
0x1800a70b3  lea     r9, [rbp+57h+ppvBits]; ppvBits
0x1800a70b7  mov     [rsp+0C0h+offset], ebx; offset
0x1800a70bb  xor     r8d, r8d; usage
0x1800a70be  mov     [rsp+0C0h+hSection], rbx; hSection
0x1800a70c3  lea     rdx, [rbp+57h+pbmi]; pbmi
0x1800a70c7  xor     ecx, ecx; hdc
0x1800a70c9  call    cs:__imp_CreateDIBSection
0x1800a70cf  mov     rcx, rdi
0x1800a70d2  mov     rbx, rax
0x1800a70d5  call    ?Empty@?$TGDIHolder@PEAUHBITMAP__@@@GDIPlus@ARC@@QEAAXXZ; ARC::GDIPlus::TGDIHolder<HBITMAP__ *>::Empty(void)
0x1800a70da  mov     [rdi], rbx
0x1800a70dd  xor     ebx, ebx
0x1800a70df  cmp     [rbp+57h+ppvBits], rbx
0x1800a70e3  jnz     short loc_1800A711B
0x1800a70e5  lea     rax, ??_7?$StructuredObject@I$00@Logging@Mso@@6B@; const Mso::Logging::StructuredObject<uint,1>::`vftable'
0x1800a70ec  mov     [rbp+57h+var_6C], bx
0x1800a70f0  mov     qword ptr [rbp+57h+var_80], rax
0x1800a70f4  lea     r8d, [r15+2]
0x1800a70f8  lea     rax, aGdipstatus; "GdipStatus"
0x1800a70ff  mov     [rbp+57h+var_70], r8d
0x1800a7103  mov     qword ptr [rbp+57h+var_80+8], rax
0x1800a7107  mov     ecx, 214967A0h
0x1800a710c  lea     rax, [rbp+57h+var_80]
0x1800a7110  mov     [rsp+0C0h+var_90], rax
0x1800a7115  call    ??$ThrowTagVariableArguments@U?$StructuredObject@I$00@Logging@Mso@@@OExceptionLog@@YAXKW4exceptionType@et@@JPEB_WW4Category@Logging@Mso@@W4Severity@45@$$QEAU?$StructuredObject@I$00@45@@Z; OExceptionLog::ThrowTagVariableArguments<Mso::Logging::StructuredObject<uint,1>>(ulong,et::exceptionType,long,wchar_t const *,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::StructuredObject<uint,1> &&)
0x1800a711b  mov     rcx, r12
0x1800a711e  call    ??I?$TGpHolder@VMatrix@Gdiplus@@@GDIPlus@ARC@@QEAAPEAPEAVMatrix@Gdiplus@@XZ; ARC::GDIPlus::TGpHolder<Gdiplus::Matrix>::operator&(void)
0x1800a7123  mov     rdx, [rbp+57h+ppvBits]
0x1800a7127  lea     rcx, [rbp+57h+pbmi]
0x1800a712b  mov     r8, rax
0x1800a712e  call    cs:__imp_GdipCreateBitmapFromGdiDib
0x1800a7134  mov     ecx, eax
0x1800a7136  mov     r9d, 25118C5h
0x1800a713c  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800a7141  mov     eax, [r14+1F0h]
0x1800a7148  lea     rdx, [rbp+57h+var_80]
0x1800a714c  mov     dword ptr [rbp+57h+var_80+8], eax
0x1800a714f  mov     rcx, r12
0x1800a7152  mov     eax, [r14+1F4h]
0x1800a7159  mov     dword ptr [rbp+57h+var_80+0Ch], eax
0x1800a715c  mov     qword ptr [rbp+57h+var_80], 0
0x1800a7164  call    ?WhiteOutBitmap@BitmapBasedPrinter@GEL@@KAXAEAV?$TGpHolder@VGpBitmap@Gdiplus@@@GDIPlus@ARC@@AEBU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@_N@Z; GEL::BitmapBasedPrinter::WhiteOutBitmap(ARC::GDIPlus::TGpHolder<Gdiplus::GpBitmap> &,Math::TRect<Math::TUnits<int,Math::DevicePixels>> const &,bool)
0x1800a7169  mov     eax, [r14+1F0h]
0x1800a7170  mov     [rsi+r13], eax
0x1800a7174  mov     eax, [r14+1F4h]
0x1800a717b  mov     [r14+1FCh], eax
0x1800a7182  mov     al, r15b
0x1800a7185  jmp     short loc_1800A7194
0x1800a7187  mov     ecx, 8591DAh; unsigned int
0x1800a718c  call    ?ThrowTag@FailureException@GEL@@SAXK@Z; GEL::FailureException::ThrowTag(ulong)
0x1800a7191  int     3; Trap to Debugger
0x1800a7192  xor     al, al
0x1800a7194  mov     rcx, [rbp+57h+var_28]
0x1800a7198  xor     rcx, rsp; StackCookie
0x1800a719b  call    __security_check_cookie
0x1800a71a0  lea     r11, [rsp+0C0h+var_20]
0x1800a71a8  mov     rbx, [r11+38h]
0x1800a71ac  mov     rsi, [r11+40h]
0x1800a71b0  mov     rdi, [r11+48h]
0x1800a71b4  mov     rsp, r11
0x1800a71b7  pop     r15
0x1800a71b9  pop     r14
0x1800a71bb  pop     r13
0x1800a71bd  pop     r12
0x1800a71bf  pop     rbp
0x1800a71c0  retn
```
