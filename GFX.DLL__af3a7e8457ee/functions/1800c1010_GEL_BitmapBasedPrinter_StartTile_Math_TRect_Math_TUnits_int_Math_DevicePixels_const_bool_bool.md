# GEL::BitmapBasedPrinter::StartTile(Math::TRect<Math::TUnits<int,Math::DevicePixels>> const &,bool,bool)

- ea: `0x1800c1010`
- end: `0x1800c1351`
- name: `?StartTile@BitmapBasedPrinter@GEL@@UEAA_NAEBU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@_N1@Z`
- size: `833`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: ``

## callees

- `0x180036950`
- `0x180050434`
- `0x180056ee0`
- `0x18005f898`
- `0x180062394`
- `0x1800629a0`
- `0x180064d9c`
- `0x1800a9b44`
- `0x1800c0860`
- `0x1800c0960`
- `0x1800c0f60`
- `0x1800c1010`
- `0x1800c21c4`
- `0x18017d458`

## import_xrefs

- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1800c107c`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1800c107c`
- `GDI32!CreateDIBSection` at `0x1800c1259`
- `GDI32!CreateDIBSection` at `0x1800c1259`
- `gdiplus!GdipCreateBitmapFromGdiDib` at `0x1800c12be`
- `gdiplus!GdipCreateBitmapFromGdiDib` at `0x1800c12be`

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
    && (byte_1805200C0 < 0
      ? Mso::AB::Optimized::FeatureGate::Evaluate((Mso::AB::Optimized::FeatureGate *)&byte_1805200C0)
      : byte_1805200C0 != 0) )
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
    v11 = (_DWORD *)sub_1800C21C4(ppvBits);
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
    v18 = 2 * *(_DWORD *)sub_1800C21C4(ppvBits);
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
0x1800c1010  mov     rax, rsp
0x1800c1013  mov     [rax+10h], rbx
0x1800c1017  mov     [rax+18h], rsi
0x1800c101b  mov     [rax+20h], rdi
0x1800c101f  push    rbp
0x1800c1020  push    r12
0x1800c1022  push    r13
0x1800c1024  push    r14
0x1800c1026  push    r15
0x1800c1028  lea     rbp, [rax-5Fh]
0x1800c102c  sub     rsp, 0A0h
0x1800c1033  mov     rax, cs:__security_cookie
0x1800c103a  xor     rax, rsp
0x1800c103d  mov     [rbp+57h+var_28], rax
0x1800c1041  xor     r13d, r13d
0x1800c1044  mov     dil, r9b
0x1800c1047  mov     bl, r8b
0x1800c104a  mov     rsi, rdx
0x1800c104d  mov     r14, rcx
0x1800c1050  cmp     [rcx+1C1h], r13b
0x1800c1057  jz      loc_1800C1322
0x1800c105d  cmp     dword ptr [rcx+140h], 3
0x1800c1064  jnz     short loc_1800C10C2
0x1800c1066  mov     al, cs:byte_1805200C0
0x1800c106c  test    al, al
0x1800c106e  js      short loc_1800C1075
0x1800c1070  setnz   al
0x1800c1073  jmp     short loc_1800C1082
0x1800c1075  lea     rcx, byte_1805200C0
0x1800c107c  call    cs:__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ; Mso::AB::Optimized::FeatureGate::Evaluate(void)
0x1800c1082  test    al, al
0x1800c1084  jz      short loc_1800C10C2
0x1800c1086  lea     rax, ??_7?$StructuredObject@I$00@Logging@Mso@@6B@; const Mso::Logging::StructuredObject<uint,1>::`vftable'
0x1800c108d  mov     [rbp+57h+var_70], 3
0x1800c1094  mov     qword ptr [rbp+57h+var_80], rax
0x1800c1098  mov     ecx, 21411694h
0x1800c109d  lea     rax, aGdipstatus; "GdipStatus"
0x1800c10a4  mov     [rbp+57h+var_6C], r13w
0x1800c10a9  mov     qword ptr [rbp+57h+var_80+8], rax
0x1800c10ad  mov     r8d, 3
0x1800c10b3  lea     rax, [rbp+57h+var_80]
0x1800c10b7  mov     [rsp+0C0h+var_90], rax
0x1800c10bc  call    ??$ThrowTagVariableArguments@U?$StructuredObject@I$00@Logging@Mso@@@OExceptionLog@@YAXKW4exceptionType@et@@JPEB_WW4Category@Logging@Mso@@W4Severity@45@$$QEAU?$StructuredObject@I$00@45@@Z; OExceptionLog::ThrowTagVariableArguments<Mso::Logging::StructuredObject<uint,1>>(ulong,et::exceptionType,long,wchar_t const *,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::StructuredObject<uint,1> &&)
0x1800c10c2  movups  xmm0, xmmword ptr [rsi]
0x1800c10c5  mov     r9b, dil
0x1800c10c8  lea     rdx, [rbp+57h+var_80]
0x1800c10cc  mov     r8b, bl
0x1800c10cf  mov     rcx, r14
0x1800c10d2  movdqu  [rbp+57h+var_80], xmm0
0x1800c10d7  call    ?StartTile@Printer@GEL@@UEAA_NAEBU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@_N1@Z; GEL::Printer::StartTile(Math::TRect<Math::TUnits<int,Math::DevicePixels>> const &,bool,bool)
0x1800c10dc  test    al, al
0x1800c10de  jz      loc_1800C1322
0x1800c10e4  mov     [r14+24Ah], bl
0x1800c10eb  test    bl, bl
0x1800c10ed  jz      short loc_1800C1100
0x1800c10ef  mov     [r14+0F0h], r13b
0x1800c10f6  mov     eax, 1
0x1800c10fb  jmp     loc_1800C1324
0x1800c1100  lea     rdx, [rbp+57h+var_80]
0x1800c1104  mov     rcx, r14
0x1800c1107  call    ?GetScalingFactor@BitmapBasedPrinter@GEL@@UEBA?AU?$TScaling2@N@Math@@XZ; GEL::BitmapBasedPrinter::GetScalingFactor(void)
0x1800c110c  movsd   xmm1, cs:__real@3ff0000000000000
0x1800c1114  lea     rdx, [r14+144h]
0x1800c111b  movaps  xmm0, xmm1
0x1800c111e  lea     r8, [rbp+57h+ppvBits]
0x1800c1122  divsd   xmm0, qword ptr [rbp+57h+var_80]
0x1800c1127  lea     rcx, [rbp+57h+pbmi]
0x1800c112b  divsd   xmm1, qword ptr [rbp+57h+var_80+8]
0x1800c1130  movsd   [rbp+57h+ppvBits], xmm0
0x1800c1135  movsd   [rbp+57h+var_60], xmm1
0x1800c113a  call    ??$?DV?$TUnits@HUDevicePixels@Math@@@Math@@NV?$TUnits@NUDevicePixels@Math@@@1@@Math@@YA?AU?$TRect@V?$TUnits@NUDevicePixels@Math@@@Math@@@0@AEBU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@0@AEBU?$TScaling2@N@0@@Z; Math::operator*<Math::TUnits<int,Math::DevicePixels>,double,Math::TUnits<double,Math::DevicePixels>>(Math::TRect<Math::TUnits<int,Math::DevicePixels>> const &,Math::TScaling2<double> const &)
0x1800c113f  mov     rdx, rax
0x1800c1142  lea     rcx, [rbp+57h+var_80]
0x1800c1146  call    ??$snap_outward_cast@V?$TUnits@HUDevicePixels@Math@@@Math@@V?$TUnits@NUDevicePixels@Math@@@2@$0A@$0A@@Math@@YA?AU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@0@AEBU?$TRect@V?$TUnits@NUDevicePixels@Math@@@Math@@@0@@Z; Math::snap_outward_cast<Math::TUnits<int,Math::DevicePixels>,Math::TUnits<double,Math::DevicePixels>,0,0>(Math::TRect<Math::TUnits<double,Math::DevicePixels>> const &)
0x1800c114b  lea     rcx, [rbp+57h+ppvBits]
0x1800c114f  call    sub_1800C21C4
0x1800c1154  mov     edi, dword ptr [rbp+57h+var_80]
0x1800c1157  mov     esi, dword ptr [rbp+57h+var_80+8]
0x1800c115a  mov     r15d, dword ptr [rbp+57h+var_80+0Ch]
0x1800c115e  mov     ecx, [rax]
0x1800c1160  mov     ebx, dword ptr [rbp+57h+var_80+4]
0x1800c1163  add     ecx, ecx
0x1800c1165  cmp     edi, esi
0x1800c1167  jg      short loc_1800C1174
0x1800c1169  cmp     ebx, r15d
0x1800c116c  jg      short loc_1800C1174
0x1800c116e  mov     eax, esi
0x1800c1170  sub     eax, edi
0x1800c1172  jmp     short loc_1800C1177
0x1800c1174  mov     eax, r13d
0x1800c1177  add     eax, ecx
0x1800c1179  lea     rcx, [rbp+57h+ppvBits]
0x1800c117d  mov     [r14+1F0h], eax
0x1800c1184  call    sub_1800C21C4
0x1800c1189  mov     ecx, [rax]
0x1800c118b  add     ecx, ecx
0x1800c118d  cmp     edi, esi
0x1800c118f  jg      short loc_1800C119B
0x1800c1191  cmp     ebx, r15d
0x1800c1194  jg      short loc_1800C119B
0x1800c1196  sub     r15d, ebx
0x1800c1199  jmp     short loc_1800C119E
0x1800c119b  mov     r15d, r13d
0x1800c119e  lea     eax, [rcx+r15]
0x1800c11a2  mov     ecx, [r14+1F0h]
0x1800c11a9  mov     [r14+1F4h], eax
0x1800c11b0  test    ecx, ecx
0x1800c11b2  js      loc_1800C1317
0x1800c11b8  test    eax, eax
0x1800c11ba  js      loc_1800C1317
0x1800c11c0  lea     r12, [r14+1E0h]
0x1800c11c7  cmp     [r12], r13
0x1800c11cb  jz      short loc_1800C11E7
0x1800c11cd  cmp     ecx, [r14+1F8h]
0x1800c11d4  jnz     short loc_1800C11DF
0x1800c11d6  cmp     eax, [r14+1FCh]
0x1800c11dd  jz      short loc_1800C11E7
0x1800c11df  mov     rcx, r12
0x1800c11e2  call    ?Empty@?$TGpHolder@VGpBitmap@Gdiplus@@@GDIPlus@ARC@@QEAAXXZ; ARC::GDIPlus::TGpHolder<Gdiplus::GpBitmap>::Empty(void)
0x1800c11e7  xor     ebx, ebx
0x1800c11e9  mov     r13, r14
0x1800c11ec  mov     esi, 1F8h
0x1800c11f1  lea     r15d, [rbx+1]
0x1800c11f5  cmp     [r12], rbx
0x1800c11f9  jnz     loc_1800C12D1
0x1800c11ff  mov     eax, [r14+1F0h]
0x1800c1206  lea     rdi, [r14+1D8h]
0x1800c120d  mov     [rbp+57h+pbmi.bmiHeader.biWidth], eax
0x1800c1210  xorps   xmm0, xmm0
0x1800c1213  mov     eax, [r14+1F4h]
0x1800c121a  mov     rcx, rdi
0x1800c121d  neg     eax
0x1800c121f  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biClrImportant], rbx
0x1800c1223  mov     [rbp+57h+pbmi.bmiHeader.biHeight], eax
0x1800c1226  movdqu  xmmword ptr [rbp+57h+pbmi.bmiHeader.biSizeImage], xmm0
0x1800c122b  mov     [rbp+57h+pbmi.bmiHeader.biSize], 28h ; '('
0x1800c1232  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biPlanes], 200001h
0x1800c123a  mov     [rbp+57h+ppvBits], rbx
0x1800c123e  call    ?Empty@?$TGDIHolder@PEAUHBITMAP__@@@GDIPlus@ARC@@QEAAXXZ; ARC::GDIPlus::TGDIHolder<HBITMAP__ *>::Empty(void)
0x1800c1243  lea     r9, [rbp+57h+ppvBits]; ppvBits
0x1800c1247  mov     [rsp+0C0h+offset], ebx; offset
0x1800c124b  xor     r8d, r8d; usage
0x1800c124e  mov     [rsp+0C0h+hSection], rbx; hSection
0x1800c1253  lea     rdx, [rbp+57h+pbmi]; pbmi
0x1800c1257  xor     ecx, ecx; hdc
0x1800c1259  call    cs:__imp_CreateDIBSection
0x1800c125f  mov     rcx, rdi
0x1800c1262  mov     rbx, rax
0x1800c1265  call    ?Empty@?$TGDIHolder@PEAUHBITMAP__@@@GDIPlus@ARC@@QEAAXXZ; ARC::GDIPlus::TGDIHolder<HBITMAP__ *>::Empty(void)
0x1800c126a  mov     [rdi], rbx
0x1800c126d  xor     ebx, ebx
0x1800c126f  cmp     [rbp+57h+ppvBits], rbx
0x1800c1273  jnz     short loc_1800C12AB
0x1800c1275  lea     rax, ??_7?$StructuredObject@I$00@Logging@Mso@@6B@; const Mso::Logging::StructuredObject<uint,1>::`vftable'
0x1800c127c  mov     [rbp+57h+var_6C], bx
0x1800c1280  mov     qword ptr [rbp+57h+var_80], rax
0x1800c1284  lea     r8d, [r15+2]
0x1800c1288  lea     rax, aGdipstatus; "GdipStatus"
0x1800c128f  mov     [rbp+57h+var_70], r8d
0x1800c1293  mov     qword ptr [rbp+57h+var_80+8], rax
0x1800c1297  mov     ecx, 214967A0h
0x1800c129c  lea     rax, [rbp+57h+var_80]
0x1800c12a0  mov     [rsp+0C0h+var_90], rax
0x1800c12a5  call    ??$ThrowTagVariableArguments@U?$StructuredObject@I$00@Logging@Mso@@@OExceptionLog@@YAXKW4exceptionType@et@@JPEB_WW4Category@Logging@Mso@@W4Severity@45@$$QEAU?$StructuredObject@I$00@45@@Z; OExceptionLog::ThrowTagVariableArguments<Mso::Logging::StructuredObject<uint,1>>(ulong,et::exceptionType,long,wchar_t const *,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::StructuredObject<uint,1> &&)
0x1800c12ab  mov     rcx, r12
0x1800c12ae  call    ??I?$TGpHolder@VMatrix@Gdiplus@@@GDIPlus@ARC@@QEAAPEAPEAVMatrix@Gdiplus@@XZ; ARC::GDIPlus::TGpHolder<Gdiplus::Matrix>::operator&(void)
0x1800c12b3  mov     rdx, [rbp+57h+ppvBits]
0x1800c12b7  lea     rcx, [rbp+57h+pbmi]
0x1800c12bb  mov     r8, rax
0x1800c12be  call    cs:__imp_GdipCreateBitmapFromGdiDib
0x1800c12c4  mov     ecx, eax
0x1800c12c6  mov     r9d, 25118C5h
0x1800c12cc  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1800c12d1  mov     eax, [r14+1F0h]
0x1800c12d8  lea     rdx, [rbp+57h+var_80]
0x1800c12dc  mov     dword ptr [rbp+57h+var_80+8], eax
0x1800c12df  mov     rcx, r12
0x1800c12e2  mov     eax, [r14+1F4h]
0x1800c12e9  mov     dword ptr [rbp+57h+var_80+0Ch], eax
0x1800c12ec  mov     qword ptr [rbp+57h+var_80], 0
0x1800c12f4  call    ?WhiteOutBitmap@BitmapBasedPrinter@GEL@@KAXAEAV?$TGpHolder@VGpBitmap@Gdiplus@@@GDIPlus@ARC@@AEBU?$TRect@V?$TUnits@HUDevicePixels@Math@@@Math@@@Math@@_N@Z; GEL::BitmapBasedPrinter::WhiteOutBitmap(ARC::GDIPlus::TGpHolder<Gdiplus::GpBitmap> &,Math::TRect<Math::TUnits<int,Math::DevicePixels>> const &,bool)
0x1800c12f9  mov     eax, [r14+1F0h]
0x1800c1300  mov     [rsi+r13], eax
0x1800c1304  mov     eax, [r14+1F4h]
0x1800c130b  mov     [r14+1FCh], eax
0x1800c1312  mov     al, r15b
0x1800c1315  jmp     short loc_1800C1324
0x1800c1317  mov     ecx, 8591DAh; unsigned int
0x1800c131c  call    ?ThrowTag@FailureException@GEL@@SAXK@Z; GEL::FailureException::ThrowTag(ulong)
0x1800c1321  int     3; Trap to Debugger
0x1800c1322  xor     al, al
0x1800c1324  mov     rcx, [rbp+57h+var_28]
0x1800c1328  xor     rcx, rsp; StackCookie
0x1800c132b  call    __security_check_cookie
0x1800c1330  lea     r11, [rsp+0C0h+var_20]
0x1800c1338  mov     rbx, [r11+38h]
0x1800c133c  mov     rsi, [r11+40h]
0x1800c1340  mov     rdi, [r11+48h]
0x1800c1344  mov     rsp, r11
0x1800c1347  pop     r15
0x1800c1349  pop     r14
0x1800c134b  pop     r13
0x1800c134d  pop     r12
0x1800c134f  pop     rbp
0x1800c1350  retn
```
