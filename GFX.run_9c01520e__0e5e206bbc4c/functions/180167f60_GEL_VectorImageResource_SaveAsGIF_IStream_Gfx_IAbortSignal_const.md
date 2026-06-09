# GEL::VectorImageResource::SaveAsGIF(IStream *,Gfx::IAbortSignal const *)

- ea: `0x180167f60`
- end: `0x1801683b0`
- name: `?SaveAsGIF@VectorImageResource@GEL@@UEBAXPEAUIStream@@PEBUIAbortSignal@Gfx@@@Z`
- size: `1104`
- prototype: `void __fastcall(GEL::VectorImageResource *__hidden this, struct IStream *, const struct Gfx::IAbortSignal *)`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x1800578b0`
- `0x18007f754`
- `0x180080960`
- `0x180081620`
- `0x180092a58`
- `0x1800aedc0`
- `0x1800dd460`
- `0x180129970`
- `0x18014c890`
- `0x180167f60`
- `0x1801d0500`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18016814b`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18016814b`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180168085`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18016839f`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180168085`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18016839f`
- `gdiplus!GdipGetImageEncoders` at `0x180168032`
- `gdiplus!GdipGetImageEncoders` at `0x180168032`
- `gdiplus!GdipGetImageEncodersSize` at `0x180167fe2`
- `gdiplus!GdipGetImageEncodersSize` at `0x180167fe2`
- `gdiplus!GdipBitmapSetPixel` at `0x180168314`
- `gdiplus!GdipBitmapSetPixel` at `0x180168314`
- `gdiplus!GdipBitmapGetPixel` at `0x18016823c`
- `gdiplus!GdipBitmapGetPixel` at `0x18016823c`
- `gdiplus!GdipGetImagePixelFormat` at `0x18016812a`
- `gdiplus!GdipGetImagePixelFormat` at `0x18016812a`
- `gdiplus!GdipSaveImageToStream` at `0x1801680a6`
- `gdiplus!GdipSaveImageToStream` at `0x180168362`
- `gdiplus!GdipSaveImageToStream` at `0x1801680a6`
- `gdiplus!GdipSaveImageToStream` at `0x180168362`
- `gdiplus!GdipImageSetAbort` at `0x180167fc4`
- `gdiplus!GdipImageSetAbort` at `0x1801680ca`
- `gdiplus!GdipImageSetAbort` at `0x180167fc4`
- `gdiplus!GdipImageSetAbort` at `0x1801680ca`
- `gdiplus!GdipDrawImageRectRectI` at `0x1801681fb`
- `gdiplus!GdipDrawImageRectRectI` at `0x1801681fb`
- `gdiplus!GdipGetImageGraphicsContext` at `0x18016818b`
- `gdiplus!GdipGetImageGraphicsContext` at `0x18016818b`
- `gdiplus!GdipSetInterpolationMode` at `0x1801681a7`
- `gdiplus!GdipSetInterpolationMode` at `0x1801681a7`
- `gdiplus!GdipDeleteGraphics` at `0x180168345`
- `gdiplus!GdipDeleteGraphics` at `0x180168345`
- `gdiplus!GdipDisposeImage` at `0x18016837f`
- `gdiplus!GdipDisposeImage` at `0x18016837f`
- `gdiplus!GdipCreateBitmapFromScan0` at `0x18016816c`
- `gdiplus!GdipCreateBitmapFromScan0` at `0x18016816c`

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
0x180167f60  mov     [rsp-8+arg_10], rbx
0x180167f65  push    rbp
0x180167f66  push    rsi
0x180167f67  push    rdi
0x180167f68  push    r12
0x180167f6a  push    r13
0x180167f6c  push    r14
0x180167f6e  push    r15
0x180167f70  lea     rbp, [rsp-27h]
0x180167f75  sub     rsp, 0D0h
0x180167f7c  mov     rax, cs:__security_cookie
0x180167f83  xor     rax, rsp
0x180167f86  mov     [rbp+57h+var_40], rax
0x180167f8a  mov     r15, rdx
0x180167f8d  mov     rdi, rcx
0x180167f90  xor     r12d, r12d
0x180167f93  cmp     [rcx+6Ah], r12b
0x180167f97  jz      short loc_180167FA4
0x180167f99  mov     ecx, 8582D9h; unsigned int
0x180167f9e  call    ?ThrowTag@FailureException@GEL@@SAXK@Z; GEL::FailureException::ThrowTag(ulong)
0x180167fa3  int     3; Trap to Debugger
0x180167fa4  mov     rcx, [rcx+8]
0x180167fa8  lea     r13, ??_7GDIPlusImageAbortRestorer@GEL@@6B@; const GEL::GDIPlusImageAbortRestorer::`vftable'
0x180167faf  mov     [rbp+57h+var_68], r13
0x180167fb3  mov     [rbp+57h+var_60], rcx
0x180167fb7  mov     [rbp+57h+var_58], r8
0x180167fbb  test    r8, r8
0x180167fbe  jz      short loc_180167FCB
0x180167fc0  lea     rdx, [rbp+57h+var_68]
0x180167fc4  call    cs:__imp_GdipImageSetAbort
0x180167fca  nop
0x180167fcb  xorps   xmm0, xmm0
0x180167fce  movups  [rbp+57h+var_50], xmm0
0x180167fd2  mov     [rbp+57h+var_90], r12d
0x180167fd6  mov     dword ptr [rbp+57h+var_80], r12d
0x180167fda  lea     rdx, [rbp+57h+var_80]
0x180167fde  lea     rcx, [rbp+57h+var_90]
0x180167fe2  call    cs:__imp_GdipGetImageEncodersSize
0x180167fe8  mov     r9d, 2545523h
0x180167fee  mov     ecx, eax
0x180167ff0  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x180167ff5  mov     edx, dword ptr [rbp+57h+var_80]; unsigned __int64
0x180167ff8  test    edx, edx
0x180167ffa  jz      loc_1801683A5
0x180168000  mov     rbx, r12
0x180168003  mov     [rbp+57h+var_70], rbx
0x180168007  mov     eax, 68h ; 'h'
0x18016800c  mul     rdx
0x18016800f  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180168016  cmovb   rax, rcx
0x18016801a  mov     rcx, rax; this
0x18016801d  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x180168022  mov     rbx, rax
0x180168025  mov     [rbp+57h+var_70], rax
0x180168029  mov     edx, dword ptr [rbp+57h+var_80]
0x18016802c  mov     r8, rax
0x18016802f  mov     ecx, [rbp+57h+var_90]
0x180168032  call    cs:__imp_GdipGetImageEncoders
0x180168038  mov     r9d, 2545540h
0x18016803e  mov     ecx, eax
0x180168040  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x180168045  mov     esi, r12d
0x180168048  cmp     esi, [rbp+57h+var_90]
0x18016804b  jnb     loc_180168397
0x180168051  mov     eax, esi
0x180168053  imul    r14, rax, 68h ; 'h'
0x180168057  xor     r8d, r8d; wchar_t *
0x18016805a  lea     rdx, aImageGif; "image/gif"
0x180168061  mov     rcx, [r14+rbx+40h]; this
0x180168066  call    ?FWzEqual@Ofc@@YA_NPEB_W0_N@Z; Ofc::FWzEqual(wchar_t const *,wchar_t const *,bool)
0x18016806b  test    al, al
0x18016806d  jnz     short loc_180168073
0x18016806f  inc     esi
0x180168071  jmp     short loc_180168048
0x180168073  movups  xmm0, xmmword ptr [r14+rbx]
0x180168078  movdqu  [rbp+57h+var_50], xmm0
0x18016807d  test    rbx, rbx
0x180168080  jz      short loc_18016808B
0x180168082  mov     rcx, rbx
0x180168085  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x18016808b  mov     rcx, rdi
0x18016808e  call    ?GetSaveFormat@VectorImageResource@GEL@@UEBA?AW4ImageFormat@2@XZ; GEL::VectorImageResource::GetSaveFormat(void)
0x180168093  cmp     eax, 2
0x180168096  jnz     short loc_1801680F7
0x180168098  xor     r9d, r9d
0x18016809b  lea     r8, [rbp+57h+var_50]
0x18016809f  mov     rdx, r15
0x1801680a2  mov     rcx, [rdi+8]
0x1801680a6  call    cs:__imp_GdipSaveImageToStream
0x1801680ac  mov     r9d, 2545554h
0x1801680b2  mov     ecx, eax
0x1801680b4  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1801680b9  nop
0x1801680ba  mov     [rbp+57h+var_68], r13
0x1801680be  cmp     [rbp+57h+var_58], r12
0x1801680c2  jz      short loc_1801680D0
0x1801680c4  xor     edx, edx
0x1801680c6  mov     rcx, [rbp+57h+var_60]
0x1801680ca  call    cs:__imp_GdipImageSetAbort
0x1801680d0  mov     rcx, [rbp+57h+var_40]
0x1801680d4  xor     rcx, rsp; StackCookie
0x1801680d7  call    __security_check_cookie
0x1801680dc  mov     rbx, [rsp+100h+arg_10]
0x1801680e4  add     rsp, 0D0h
0x1801680eb  pop     r15
0x1801680ed  pop     r14
0x1801680ef  pop     r13
0x1801680f1  pop     r12
0x1801680f3  pop     rdi
0x1801680f4  pop     rsi
0x1801680f5  pop     rbp
0x1801680f6  retn
0x1801680f7  mov     [rbp+57h+var_78], r12d
0x1801680fb  mov     [rbp+57h+var_88], r12
0x1801680ff  lea     rdx, [rbp+57h+var_70]
0x180168103  mov     rcx, rdi
0x180168106  call    ?GetSize@VectorImageResource@GEL@@UEBA?AU?$TSize@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@XZ; GEL::VectorImageResource::GetSize(void)
0x18016810b  lea     rcx, [rbp+57h+var_70]
0x18016810f  call    ??$SafeCast@HI@Math@@YAHAEBI@Z; Math::SafeCast<int,uint>(uint const &)
0x180168114  mov     esi, eax
0x180168116  lea     rcx, [rbp+57h+var_70+4]
0x18016811a  call    ??$SafeCast@HI@Math@@YAHAEBI@Z; Math::SafeCast<int,uint>(uint const &)
0x18016811f  mov     r14d, eax
0x180168122  lea     rdx, [rbp+57h+var_78]
0x180168126  mov     rcx, [rdi+8]
0x18016812a  call    cs:__imp_GdipGetImagePixelFormat
0x180168130  mov     r9d, 2545555h
0x180168136  mov     ecx, eax
0x180168138  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18016813d  nop
0x18016813e  cmp     [rbp+57h+var_88], r12
0x180168142  jz      short loc_180168152
0x180168144  xor     edx, edx
0x180168146  mov     ecx, 1E55E058h
0x18016814b  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180168151  nop
0x180168152  lea     rax, [rbp+57h+var_88]
0x180168156  mov     [rsp+100h+var_D8], rax
0x18016815b  mov     [rsp+100h+var_E0], r12
0x180168160  mov     r9d, [rbp+57h+var_78]
0x180168164  xor     r8d, r8d
0x180168167  mov     edx, r14d
0x18016816a  mov     ecx, esi
0x18016816c  call    cs:__imp_GdipCreateBitmapFromScan0
0x180168172  mov     r9d, 2545556h
0x180168178  mov     ecx, eax
0x18016817a  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18016817f  mov     [rbp+57h+var_80], r12
0x180168183  lea     rdx, [rbp+57h+var_80]
0x180168187  mov     rcx, [rbp+57h+var_88]
0x18016818b  call    cs:__imp_GdipGetImageGraphicsContext
0x180168191  mov     r9d, 248C153h
0x180168197  mov     ecx, eax
0x180168199  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18016819e  mov     edx, 5
0x1801681a3  mov     rcx, [rbp+57h+var_80]
0x1801681a7  call    cs:__imp_GdipSetInterpolationMode
0x1801681ad  mov     r9d, 2545557h
0x1801681b3  mov     ecx, eax
0x1801681b5  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1801681ba  mov     [rsp+100h+var_98], r12
0x1801681bf  mov     [rsp+100h+var_A0], r12
0x1801681c4  mov     [rsp+100h+var_A8], r12
0x1801681c9  mov     [rsp+100h+var_B0], 2
0x1801681d1  mov     [rsp+100h+var_B8], r14d
0x1801681d6  mov     [rsp+100h+var_C0], esi
0x1801681da  mov     [rsp+100h+var_C8], r12d
0x1801681df  mov     [rsp+100h+var_D0], r12d
0x1801681e4  mov     dword ptr [rsp+100h+var_D8], r14d
0x1801681e9  mov     dword ptr [rsp+100h+var_E0], esi
0x1801681ed  xor     r9d, r9d
0x1801681f0  xor     r8d, r8d
0x1801681f3  mov     rdx, [rdi+8]
0x1801681f7  mov     rcx, [rbp+57h+var_80]
0x1801681fb  call    cs:__imp_GdipDrawImageRectRectI
0x180168201  mov     r9d, 2545558h
0x180168207  mov     ecx, eax
0x180168209  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18016820e  mov     ebx, r12d
0x180168211  test    r14d, r14d
0x180168214  jle     loc_18016833C
0x18016821a  mov     r13d, 0FFh
0x180168220  mov     edi, r12d
0x180168223  test    esi, esi
0x180168225  jle     loc_180168331
0x18016822b  mov     [rbp+57h+var_90], r12d
0x18016822f  lea     r9, [rbp+57h+var_90]
0x180168233  mov     r8d, ebx
0x180168236  mov     edx, edi
0x180168238  mov     rcx, [rbp+57h+var_88]
0x18016823c  call    cs:__imp_GdipBitmapGetPixel
0x180168242  mov     r9d, 2545559h
0x180168248  mov     ecx, eax
0x18016824a  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x18016824f  mov     r11d, [rbp+57h+var_90]
0x180168253  mov     eax, r11d
0x180168256  shr     eax, 18h
0x180168259  test    al, al
0x18016825b  jz      loc_180168308
0x180168261  mov     r9d, eax
0x180168264  mov     eax, r11d
0x180168267  shr     eax, 10h
0x18016826a  movzx   ecx, al
0x18016826d  sub     ecx, r13d
0x180168270  imul    ecx, r9d
0x180168274  mov     r8d, 0FE01h
0x18016827a  add     ecx, r8d
0x18016827d  mov     eax, 80808081h
0x180168282  imul    ecx
0x180168284  lea     r10d, [rcx+rdx]
0x180168288  sar     r10d, 7
0x18016828c  mov     eax, r10d
0x18016828f  shr     eax, 1Fh
0x180168292  add     r10d, eax
0x180168295  mov     eax, r11d
0x180168298  shr     eax, 8
0x18016829b  movzx   ecx, al
0x18016829e  sub     ecx, r13d
0x1801682a1  imul    ecx, r9d
0x1801682a5  add     ecx, r8d
0x1801682a8  mov     eax, 80808081h
0x1801682ad  imul    ecx
0x1801682af  lea     r8d, [rcx+rdx]
0x1801682b3  sar     r8d, 7
0x1801682b7  mov     eax, r8d
0x1801682ba  shr     eax, 1Fh
0x1801682bd  add     r8d, eax
0x1801682c0  movzx   ecx, r11b
0x1801682c4  sub     ecx, r13d
0x1801682c7  imul    ecx, r9d
0x1801682cb  add     ecx, 0FE01h
0x1801682d1  mov     eax, 80808081h
0x1801682d6  imul    ecx
0x1801682d8  add     edx, ecx
0x1801682da  sar     edx, 7
0x1801682dd  mov     eax, edx
0x1801682df  shr     eax, 1Fh
0x1801682e2  add     edx, eax
0x1801682e4  movzx   r11d, r10b
0x1801682e8  or      r11d, 0FFFFFF00h
0x1801682ef  shl     r11d, 8
0x1801682f3  movzx   eax, r8b
0x1801682f7  or      r11d, eax
0x1801682fa  shl     r11d, 8
0x1801682fe  movzx   eax, dl
0x180168301  or      r11d, eax
0x180168304  mov     [rbp+57h+var_90], r11d
0x180168308  mov     r9d, r11d
0x18016830b  mov     r8d, ebx
0x18016830e  mov     edx, edi
0x180168310  mov     rcx, [rbp+57h+var_88]
0x180168314  call    cs:__imp_GdipBitmapSetPixel
0x18016831a  mov     r9d, 254555Ah
0x180168320  mov     ecx, eax
0x180168322  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x180168327  inc     edi
0x180168329  cmp     edi, esi
0x18016832b  jl      loc_18016822B
0x180168331  inc     ebx
0x180168333  cmp     ebx, r14d
0x180168336  jl      loc_180168220
0x18016833c  mov     rcx, [rbp+57h+var_80]
0x180168340  test    rcx, rcx
0x180168343  jz      short loc_18016834B
0x180168345  call    cs:__imp_GdipDeleteGraphics
0x18016834b  lea     rcx, [rbp+57h+var_88]
0x18016834f  call    ?ConvertBitmapToIndexedFormat@VectorImageResource@GEL@@CAXAEAV?$TGpHolder@VGpBitmap@Gdiplus@@@GDIPlus@ARC@@H_N@Z; GEL::VectorImageResource::ConvertBitmapToIndexedFormat(ARC::GDIPlus::TGpHolder<Gdiplus::GpBitmap> &,int,bool)
0x180168354  xor     r9d, r9d
0x180168357  lea     r8, [rbp+57h+var_50]
0x18016835b  mov     rdx, r15
0x18016835e  mov     rcx, [rbp+57h+var_88]
0x180168362  call    cs:__imp_GdipSaveImageToStream
0x180168368  mov     r9d, 254555Bh
0x18016836e  mov     ecx, eax
0x180168370  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x180168375  nop
0x180168376  mov     rcx, [rbp+57h+var_88]
0x18016837a  test    rcx, rcx
0x18016837d  jz      short loc_180168389
0x18016837f  call    cs:__imp_GdipDisposeImage
0x180168385  mov     [rbp+57h+var_88], r12
0x180168389  lea     rcx, [rbp+57h+var_68]; this
0x18016838d  call    ??1GDIPlusImageAbortRestorer@GEL@@UEAA@XZ; GEL::GDIPlusImageAbortRestorer::~GDIPlusImageAbortRestorer(void)
0x180168392  jmp     loc_1801680D0
0x180168397  test    rbx, rbx
0x18016839a  jz      short loc_1801683A5
0x18016839c  mov     rcx, rbx
0x18016839f  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x1801683a5  mov     ecx, 8582DAh; unsigned int
0x1801683aa  call    ?ThrowTag@FailureException@GEL@@SAXK@Z; GEL::FailureException::ThrowTag(ulong)
0x1801683af  int     3; Trap to Debugger
```
