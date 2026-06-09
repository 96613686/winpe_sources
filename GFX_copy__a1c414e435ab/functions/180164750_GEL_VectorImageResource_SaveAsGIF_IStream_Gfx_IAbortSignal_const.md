# GEL::VectorImageResource::SaveAsGIF(IStream *,Gfx::IAbortSignal const *)

- ea: `0x180164750`
- end: `0x180164ba0`
- name: `?SaveAsGIF@VectorImageResource@GEL@@UEBAXPEAUIStream@@PEBUIAbortSignal@Gfx@@@Z`
- size: `1104`
- prototype: `void __fastcall(GEL::VectorImageResource *__hidden this, struct IStream *, const struct Gfx::IAbortSignal *)`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x180056ee0`
- `0x180060840`
- `0x180060f10`
- `0x180062394`
- `0x1800786fc`
- `0x180099c8c`
- `0x1800a9b44`
- `0x18012bce0`
- `0x18014b830`
- `0x180164750`
- `0x1801cb960`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18016493b`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18016493b`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180164875`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180164b8f`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180164875`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180164b8f`
- `gdiplus!GdipGetImageEncoders` at `0x180164822`
- `gdiplus!GdipGetImageEncoders` at `0x180164822`
- `gdiplus!GdipGetImageEncodersSize` at `0x1801647d2`
- `gdiplus!GdipGetImageEncodersSize` at `0x1801647d2`
- `gdiplus!GdipBitmapSetPixel` at `0x180164b04`
- `gdiplus!GdipBitmapSetPixel` at `0x180164b04`
- `gdiplus!GdipBitmapGetPixel` at `0x180164a2c`
- `gdiplus!GdipBitmapGetPixel` at `0x180164a2c`
- `gdiplus!GdipGetImagePixelFormat` at `0x18016491a`
- `gdiplus!GdipGetImagePixelFormat` at `0x18016491a`
- `gdiplus!GdipSaveImageToStream` at `0x180164896`
- `gdiplus!GdipSaveImageToStream` at `0x180164b52`
- `gdiplus!GdipSaveImageToStream` at `0x180164896`
- `gdiplus!GdipSaveImageToStream` at `0x180164b52`
- `gdiplus!GdipImageSetAbort` at `0x1801647b4`
- `gdiplus!GdipImageSetAbort` at `0x1801648ba`
- `gdiplus!GdipImageSetAbort` at `0x1801647b4`
- `gdiplus!GdipImageSetAbort` at `0x1801648ba`
- `gdiplus!GdipDrawImageRectRectI` at `0x1801649eb`
- `gdiplus!GdipDrawImageRectRectI` at `0x1801649eb`
- `gdiplus!GdipGetImageGraphicsContext` at `0x18016497b`
- `gdiplus!GdipGetImageGraphicsContext` at `0x18016497b`
- `gdiplus!GdipSetInterpolationMode` at `0x180164997`
- `gdiplus!GdipSetInterpolationMode` at `0x180164997`
- `gdiplus!GdipDeleteGraphics` at `0x180164b35`
- `gdiplus!GdipDeleteGraphics` at `0x180164b35`
- `gdiplus!GdipDisposeImage` at `0x180164b6f`
- `gdiplus!GdipDisposeImage` at `0x180164b6f`
- `gdiplus!GdipCreateBitmapFromScan0` at `0x18016495c`
- `gdiplus!GdipCreateBitmapFromScan0` at `0x18016495c`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall GEL::VectorImageResource::SaveAsGIF(
        GEL::VectorImageResource *this,
        struct IStream *a2,
        const struct Gfx::IAbortSignal *a3)
{
  __int64 v5; // rcx
  unsigned int ImageEncodersSize; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  unsigned int v9; // r8d
  unsigned __int128 v10; // rax
  Mso::Memory *v11; // rbx
  unsigned int ImageEncoders; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  void *v15; // rdx
  bool v16; // r9
  unsigned int i; // esi
  __int64 v18; // r14
  unsigned int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // r8
  unsigned int v22; // esi
  unsigned int v23; // r14d
  unsigned int ImagePixelFormat; // eax
  __int64 v25; // rdx
  __int64 v26; // r8
  unsigned int v27; // eax
  __int64 v28; // rdx
  __int64 v29; // r8
  unsigned int ImageGraphicsContext; // eax
  __int64 v31; // rdx
  __int64 v32; // r8
  unsigned int v33; // eax
  __int64 v34; // rdx
  __int64 v35; // r8
  unsigned int v36; // eax
  __int64 v37; // rdx
  __int64 v38; // r8
  unsigned int j; // ebx
  unsigned int k; // edi
  unsigned int Pixel; // eax
  __int64 v42; // rdx
  __int64 v43; // r8
  unsigned int v44; // r11d
  unsigned int v45; // eax
  __int64 v46; // rdx
  __int64 v47; // r8
  unsigned int v48; // eax
  __int64 v49; // rdx
  __int64 v50; // r8
  unsigned int v51; // [rsp+70h] [rbp-39h] BYREF
  __int64 v52; // [rsp+78h] [rbp-31h] BYREF
  unsigned __int64 v53; // [rsp+80h] [rbp-29h] BYREF
  unsigned int v54; // [rsp+88h] [rbp-21h] BYREF
  Mso::Memory *v55; // [rsp+90h] [rbp-19h] BYREF
  void **v56; // [rsp+98h] [rbp-11h] BYREF
  __int64 v57; // [rsp+A0h] [rbp-9h]
  const struct Gfx::IAbortSignal *v58; // [rsp+A8h] [rbp-1h]
  __int128 v59; // [rsp+B0h] [rbp+7h] BYREF

  if ( *((_BYTE *)this + 106) )
  {
    GEL::FailureException::ThrowTag(0x8582D9u);
    __debugbreak();
  }
  v5 = *((_QWORD *)this + 1);
  v56 = &GEL::GDIPlusImageAbortRestorer::`vftable';
  v57 = v5;
  v58 = a3;
  if ( a3 )
    GdipImageSetAbort(v5, &v56);
  v59 = 0;
  v51 = 0;
  LODWORD(v53) = 0;
  ImageEncodersSize = GdipGetImageEncodersSize(&v51, &v53);
  Gfx::GdipStatus_ThrowOnFailureMessageTag(ImageEncodersSize, v7, v8, 39081251);
  if ( !(_DWORD)v53 )
  {
LABEL_33:
    GEL::FailureException::ThrowTag(0x8582DAu);
    __debugbreak();
  }
  v55 = 0;
  v10 = (unsigned int)v53 * (unsigned __int128)0x68uLL;
  if ( !is_mul_ok((unsigned int)v53, 0x68u) )
    *(_QWORD *)&v10 = -1;
  v11 = (Mso::Memory *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)v10, *((unsigned __int64 *)&v10 + 1), v9);
  v55 = v11;
  ImageEncoders = GdipGetImageEncoders(v51, (unsigned int)v53, v11);
  Gfx::GdipStatus_ThrowOnFailureMessageTag(ImageEncoders, v13, v14, 39081280);
  for ( i = 0; ; ++i )
  {
    if ( i >= v51 )
    {
      if ( v11 )
        Mso::Memory::Free(v11, v15);
      goto LABEL_33;
    }
    v18 = 104LL * i;
    if ( Ofc::FWzEqual(*(Ofc **)((char *)v11 + v18 + 64), L"image/gif", 0, v16) )
      break;
  }
  v59 = *(_OWORD *)((char *)v11 + v18);
  if ( v11 )
    Mso::Memory::Free(v11, v15);
  if ( (unsigned int)GEL::VectorImageResource::GetSaveFormat(this) == 2 )
  {
    v19 = GdipSaveImageToStream(*((_QWORD *)this + 1), a2, &v59, 0);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(v19, v20, v21, 39081300);
    v56 = &GEL::GDIPlusImageAbortRestorer::`vftable';
    if ( v58 )
      GdipImageSetAbort(v57, 0);
  }
  else
  {
    v54 = 0;
    v52 = 0;
    GEL::VectorImageResource::GetSize(this, &v55);
    v22 = Math::SafeCast<int,unsigned int>(&v55);
    v23 = Math::SafeCast<int,unsigned int>((char *)&v55 + 4);
    ImagePixelFormat = GdipGetImagePixelFormat(*((_QWORD *)this + 1), &v54);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(ImagePixelFormat, v25, v26, 39081301);
    if ( v52 )
      CrashWithRecovery(0x1E55E058u, 0);
    v27 = GdipCreateBitmapFromScan0(v22, v23, 0, v54, 0, &v52);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(v27, v28, v29, 39081302);
    v53 = 0;
    ImageGraphicsContext = GdipGetImageGraphicsContext(v52, &v53);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(ImageGraphicsContext, v31, v32, 38322515);
    v33 = GdipSetInterpolationMode(v53, 5);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(v33, v34, v35, 39081303);
    v36 = GdipDrawImageRectRectI(v53, *((_QWORD *)this + 1), 0, 0, v22, v23, 0, 0, v22, v23, 2, 0, 0, 0);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(v36, v37, v38, 39081304);
    for ( j = 0; (int)j < (int)v23; ++j )
    {
      for ( k = 0; (int)k < (int)v22; ++k )
      {
        v51 = 0;
        Pixel = GdipBitmapGetPixel(v52, k, j, &v51);
        Gfx::GdipStatus_ThrowOnFailureMessageTag(Pixel, v42, v43, 39081305);
        v44 = v51;
        if ( HIBYTE(v51) )
        {
          v44 = (unsigned __int8)((int)(HIBYTE(v51) * ((unsigned __int8)v51 - 255) + 65025) / 255)
              | (((unsigned __int8)((int)(HIBYTE(v51) * (BYTE1(v51) - 255) + 65025) / 255)
                | ((((int)(HIBYTE(v51) * (BYTE2(v51) - 255) + 65025) / 255) | 0xFFFFFF00) << 8)) << 8);
          v51 = v44;
        }
        v45 = GdipBitmapSetPixel(v52, k, j, v44);
        Gfx::GdipStatus_ThrowOnFailureMessageTag(v45, v46, v47, 39081306);
      }
    }
    if ( v53 )
      GdipDeleteGraphics();
    GEL::VectorImageResource::ConvertBitmapToIndexedFormat(&v52);
    v48 = GdipSaveImageToStream(v52, a2, &v59, 0);
    Gfx::GdipStatus_ThrowOnFailureMessageTag(v48, v49, v50, 39081307);
    if ( v52 )
    {
      GdipDisposeImage();
      v52 = 0;
    }
    GEL::GDIPlusImageAbortRestorer::~GDIPlusImageAbortRestorer((GEL::GDIPlusImageAbortRestorer *)&v56);
  }
}

```

## disassembly

```asm
0x180164750  mov     [rsp-8+arg_10], rbx
0x180164755  push    rbp
0x180164756  push    rsi
0x180164757  push    rdi
0x180164758  push    r12
0x18016475a  push    r13
0x18016475c  push    r14
0x18016475e  push    r15
0x180164760  lea     rbp, [rsp-27h]
0x180164765  sub     rsp, 0D0h
0x18016476c  mov     rax, cs:__security_cookie
0x180164773  xor     rax, rsp
0x180164776  mov     [rbp+57h+var_40], rax
0x18016477a  mov     r15, rdx
0x18016477d  mov     rdi, rcx
0x180164780  xor     r12d, r12d
0x180164783  cmp     [rcx+6Ah], r12b
0x180164787  jz      short loc_180164794
0x180164789  mov     ecx, 8582D9h; unsigned int
0x18016478e  call    ?ThrowTag@FailureException@GEL@@SAXK@Z; GEL::FailureException::ThrowTag(ulong)
0x180164793  int     3; Trap to Debugger
0x180164794  mov     rcx, [rcx+8]
0x180164798  lea     r13, ??_7GDIPlusImageAbortRestorer@GEL@@6B@; const GEL::GDIPlusImageAbortRestorer::`vftable'
0x18016479f  mov     [rbp+57h+var_68], r13
0x1801647a3  mov     [rbp+57h+var_60], rcx
0x1801647a7  mov     [rbp+57h+var_58], r8
0x1801647ab  test    r8, r8
0x1801647ae  jz      short loc_1801647BB
0x1801647b0  lea     rdx, [rbp+57h+var_68]
0x1801647b4  call    cs:__imp_GdipImageSetAbort
0x1801647ba  nop
0x1801647bb  xorps   xmm0, xmm0
0x1801647be  movups  [rbp+57h+var_50], xmm0
0x1801647c2  mov     [rbp+57h+var_90], r12d
0x1801647c6  mov     dword ptr [rbp+57h+var_80], r12d
0x1801647ca  lea     rdx, [rbp+57h+var_80]
0x1801647ce  lea     rcx, [rbp+57h+var_90]
0x1801647d2  call    cs:__imp_GdipGetImageEncodersSize
0x1801647d8  mov     r9d, 2545523h
0x1801647de  mov     ecx, eax
0x1801647e0  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1801647e5  mov     edx, dword ptr [rbp+57h+var_80]; unsigned __int64
0x1801647e8  test    edx, edx
0x1801647ea  jz      loc_180164B95
0x1801647f0  mov     rbx, r12
0x1801647f3  mov     [rbp+57h+var_70], rbx
0x1801647f7  mov     eax, 68h ; 'h'
0x1801647fc  mul     rdx
0x1801647ff  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180164806  cmovb   rax, rcx
0x18016480a  mov     rcx, rax; this
0x18016480d  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x180164812  mov     rbx, rax
0x180164815  mov     [rbp+57h+var_70], rax
0x180164819  mov     edx, dword ptr [rbp+57h+var_80]
0x18016481c  mov     r8, rax
0x18016481f  mov     ecx, [rbp+57h+var_90]
0x180164822  call    cs:__imp_GdipGetImageEncoders
0x180164828  mov     r9d, 2545540h
0x18016482e  mov     ecx, eax
0x180164830  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x180164835  mov     esi, r12d
0x180164838  cmp     esi, [rbp+57h+var_90]
0x18016483b  jnb     loc_180164B87
0x180164841  mov     eax, esi
0x180164843  imul    r14, rax, 68h ; 'h'
0x180164847  xor     r8d, r8d; wchar_t *
0x18016484a  lea     rdx, aImageGif; "image/gif"
0x180164851  mov     rcx, [r14+rbx+40h]; this
0x180164856  call    ?FWzEqual@Ofc@@YA_NPEB_W0_N@Z; Ofc::FWzEqual(wchar_t const *,wchar_t const *,bool)
0x18016485b  test    al, al
0x18016485d  jnz     short loc_180164863
0x18016485f  inc     esi
0x180164861  jmp     short loc_180164838
0x180164863  movups  xmm0, xmmword ptr [r14+rbx]
0x180164868  movdqu  [rbp+57h+var_50], xmm0
0x18016486d  test    rbx, rbx
0x180164870  jz      short loc_18016487B
0x180164872  mov     rcx, rbx
0x180164875  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x18016487b  mov     rcx, rdi
0x18016487e  call    ?GetSaveFormat@VectorImageResource@GEL@@UEBA?AW4ImageFormat@2@XZ; GEL::VectorImageResource::GetSaveFormat(void)
0x180164883  cmp     eax, 2
0x180164886  jnz     short loc_1801648E7
0x180164888  xor     r9d, r9d
0x18016488b  lea     r8, [rbp+57h+var_50]
0x18016488f  mov     rdx, r15
0x180164892  mov     rcx, [rdi+8]
0x180164896  call    cs:__imp_GdipSaveImageToStream
0x18016489c  mov     r9d, 2545554h
0x1801648a2  mov     ecx, eax
0x1801648a4  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1801648a9  nop
0x1801648aa  mov     [rbp+57h+var_68], r13
0x1801648ae  cmp     [rbp+57h+var_58], r12
0x1801648b2  jz      short loc_1801648C0
0x1801648b4  xor     edx, edx
0x1801648b6  mov     rcx, [rbp+57h+var_60]
0x1801648ba  call    cs:__imp_GdipImageSetAbort
0x1801648c0  mov     rcx, [rbp+57h+var_40]
0x1801648c4  xor     rcx, rsp; StackCookie
0x1801648c7  call    __security_check_cookie
0x1801648cc  mov     rbx, [rsp+100h+arg_10]
0x1801648d4  add     rsp, 0D0h
0x1801648db  pop     r15
0x1801648dd  pop     r14
0x1801648df  pop     r13
0x1801648e1  pop     r12
0x1801648e3  pop     rdi
0x1801648e4  pop     rsi
0x1801648e5  pop     rbp
0x1801648e6  retn
0x1801648e7  mov     [rbp+57h+var_78], r12d
0x1801648eb  mov     [rbp+57h+var_88], r12
0x1801648ef  lea     rdx, [rbp+57h+var_70]
0x1801648f3  mov     rcx, rdi
0x1801648f6  call    ?GetSize@VectorImageResource@GEL@@UEBA?AU?$TSize@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@XZ; GEL::VectorImageResource::GetSize(void)
0x1801648fb  lea     rcx, [rbp+57h+var_70]
0x1801648ff  call    ??$SafeCast@HI@Math@@YAHAEBI@Z; Math::SafeCast<int,uint>(uint const &)
0x180164904  mov     esi, eax
0x180164906  lea     rcx, [rbp+57h+var_70+4]
0x18016490a  call    ??$SafeCast@HI@Math@@YAHAEBI@Z; Math::SafeCast<int,uint>(uint const &)
0x18016490f  mov     r14d, eax
0x180164912  lea     rdx, [rbp+57h+var_78]
0x180164916  mov     rcx, [rdi+8]
0x18016491a  call    cs:__imp_GdipGetImagePixelFormat
0x180164920  mov     r9d, 2545555h
0x180164926  mov     ecx, eax
0x180164928  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18016492d  nop
0x18016492e  cmp     [rbp+57h+var_88], r12
0x180164932  jz      short loc_180164942
0x180164934  xor     edx, edx
0x180164936  mov     ecx, 1E55E058h
0x18016493b  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180164941  nop
0x180164942  lea     rax, [rbp+57h+var_88]
0x180164946  mov     [rsp+100h+var_D8], rax
0x18016494b  mov     [rsp+100h+var_E0], r12
0x180164950  mov     r9d, [rbp+57h+var_78]
0x180164954  xor     r8d, r8d
0x180164957  mov     edx, r14d
0x18016495a  mov     ecx, esi
0x18016495c  call    cs:__imp_GdipCreateBitmapFromScan0
0x180164962  mov     r9d, 2545556h
0x180164968  mov     ecx, eax
0x18016496a  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18016496f  mov     [rbp+57h+var_80], r12
0x180164973  lea     rdx, [rbp+57h+var_80]
0x180164977  mov     rcx, [rbp+57h+var_88]
0x18016497b  call    cs:__imp_GdipGetImageGraphicsContext
0x180164981  mov     r9d, 248C153h
0x180164987  mov     ecx, eax
0x180164989  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18016498e  mov     edx, 5
0x180164993  mov     rcx, [rbp+57h+var_80]
0x180164997  call    cs:__imp_GdipSetInterpolationMode
0x18016499d  mov     r9d, 2545557h
0x1801649a3  mov     ecx, eax
0x1801649a5  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1801649aa  mov     [rsp+100h+var_98], r12
0x1801649af  mov     [rsp+100h+var_A0], r12
0x1801649b4  mov     [rsp+100h+var_A8], r12
0x1801649b9  mov     [rsp+100h+var_B0], 2
0x1801649c1  mov     [rsp+100h+var_B8], r14d
0x1801649c6  mov     [rsp+100h+var_C0], esi
0x1801649ca  mov     [rsp+100h+var_C8], r12d
0x1801649cf  mov     [rsp+100h+var_D0], r12d
0x1801649d4  mov     dword ptr [rsp+100h+var_D8], r14d
0x1801649d9  mov     dword ptr [rsp+100h+var_E0], esi
0x1801649dd  xor     r9d, r9d
0x1801649e0  xor     r8d, r8d
0x1801649e3  mov     rdx, [rdi+8]
0x1801649e7  mov     rcx, [rbp+57h+var_80]
0x1801649eb  call    cs:__imp_GdipDrawImageRectRectI
0x1801649f1  mov     r9d, 2545558h
0x1801649f7  mov     ecx, eax
0x1801649f9  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1801649fe  mov     ebx, r12d
0x180164a01  test    r14d, r14d
0x180164a04  jle     loc_180164B2C
0x180164a0a  mov     r13d, 0FFh
0x180164a10  mov     edi, r12d
0x180164a13  test    esi, esi
0x180164a15  jle     loc_180164B21
0x180164a1b  mov     [rbp+57h+var_90], r12d
0x180164a1f  lea     r9, [rbp+57h+var_90]
0x180164a23  mov     r8d, ebx
0x180164a26  mov     edx, edi
0x180164a28  mov     rcx, [rbp+57h+var_88]
0x180164a2c  call    cs:__imp_GdipBitmapGetPixel
0x180164a32  mov     r9d, 2545559h
0x180164a38  mov     ecx, eax
0x180164a3a  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x180164a3f  mov     r11d, [rbp+57h+var_90]
0x180164a43  mov     eax, r11d
0x180164a46  shr     eax, 18h
0x180164a49  test    al, al
0x180164a4b  jz      loc_180164AF8
0x180164a51  mov     r9d, eax
0x180164a54  mov     eax, r11d
0x180164a57  shr     eax, 10h
0x180164a5a  movzx   ecx, al
0x180164a5d  sub     ecx, r13d
0x180164a60  imul    ecx, r9d
0x180164a64  mov     r8d, 0FE01h
0x180164a6a  add     ecx, r8d
0x180164a6d  mov     eax, 80808081h
0x180164a72  imul    ecx
0x180164a74  lea     r10d, [rcx+rdx]
0x180164a78  sar     r10d, 7
0x180164a7c  mov     eax, r10d
0x180164a7f  shr     eax, 1Fh
0x180164a82  add     r10d, eax
0x180164a85  mov     eax, r11d
0x180164a88  shr     eax, 8
0x180164a8b  movzx   ecx, al
0x180164a8e  sub     ecx, r13d
0x180164a91  imul    ecx, r9d
0x180164a95  add     ecx, r8d
0x180164a98  mov     eax, 80808081h
0x180164a9d  imul    ecx
0x180164a9f  lea     r8d, [rcx+rdx]
0x180164aa3  sar     r8d, 7
0x180164aa7  mov     eax, r8d
0x180164aaa  shr     eax, 1Fh
0x180164aad  add     r8d, eax
0x180164ab0  movzx   ecx, r11b
0x180164ab4  sub     ecx, r13d
0x180164ab7  imul    ecx, r9d
0x180164abb  add     ecx, 0FE01h
0x180164ac1  mov     eax, 80808081h
0x180164ac6  imul    ecx
0x180164ac8  add     edx, ecx
0x180164aca  sar     edx, 7
0x180164acd  mov     eax, edx
0x180164acf  shr     eax, 1Fh
0x180164ad2  add     edx, eax
0x180164ad4  movzx   r11d, r10b
0x180164ad8  or      r11d, 0FFFFFF00h
0x180164adf  shl     r11d, 8
0x180164ae3  movzx   eax, r8b
0x180164ae7  or      r11d, eax
0x180164aea  shl     r11d, 8
0x180164aee  movzx   eax, dl
0x180164af1  or      r11d, eax
0x180164af4  mov     [rbp+57h+var_90], r11d
0x180164af8  mov     r9d, r11d
0x180164afb  mov     r8d, ebx
0x180164afe  mov     edx, edi
0x180164b00  mov     rcx, [rbp+57h+var_88]
0x180164b04  call    cs:__imp_GdipBitmapSetPixel
0x180164b0a  mov     r9d, 254555Ah
0x180164b10  mov     ecx, eax
0x180164b12  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x180164b17  inc     edi
0x180164b19  cmp     edi, esi
0x180164b1b  jl      loc_180164A1B
0x180164b21  inc     ebx
0x180164b23  cmp     ebx, r14d
0x180164b26  jl      loc_180164A10
0x180164b2c  mov     rcx, [rbp+57h+var_80]
0x180164b30  test    rcx, rcx
0x180164b33  jz      short loc_180164B3B
0x180164b35  call    cs:__imp_GdipDeleteGraphics
0x180164b3b  lea     rcx, [rbp+57h+var_88]
0x180164b3f  call    ?ConvertBitmapToIndexedFormat@VectorImageResource@GEL@@CAXAEAV?$TGpHolder@VGpBitmap@Gdiplus@@@GDIPlus@ARC@@H_N@Z; GEL::VectorImageResource::ConvertBitmapToIndexedFormat(ARC::GDIPlus::TGpHolder<Gdiplus::GpBitmap> &,int,bool)
0x180164b44  xor     r9d, r9d
0x180164b47  lea     r8, [rbp+57h+var_50]
0x180164b4b  mov     rdx, r15
0x180164b4e  mov     rcx, [rbp+57h+var_88]
0x180164b52  call    cs:__imp_GdipSaveImageToStream
0x180164b58  mov     r9d, 254555Bh
0x180164b5e  mov     ecx, eax
0x180164b60  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x180164b65  nop
0x180164b66  mov     rcx, [rbp+57h+var_88]
0x180164b6a  test    rcx, rcx
0x180164b6d  jz      short loc_180164B79
0x180164b6f  call    cs:__imp_GdipDisposeImage
0x180164b75  mov     [rbp+57h+var_88], r12
0x180164b79  lea     rcx, [rbp+57h+var_68]; this
0x180164b7d  call    ??1GDIPlusImageAbortRestorer@GEL@@UEAA@XZ; GEL::GDIPlusImageAbortRestorer::~GDIPlusImageAbortRestorer(void)
0x180164b82  jmp     loc_1801648C0
0x180164b87  test    rbx, rbx
0x180164b8a  jz      short loc_180164B95
0x180164b8c  mov     rcx, rbx
0x180164b8f  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x180164b95  mov     ecx, 8582DAh; unsigned int
0x180164b9a  call    ?ThrowTag@FailureException@GEL@@SAXK@Z; GEL::FailureException::ThrowTag(ulong)
0x180164b9f  int     3; Trap to Debugger
```
