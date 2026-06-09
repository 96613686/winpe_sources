# GEL::VectorImageResource::AnalyzeMetafileForSpecialROPs(Gdiplus::EmfPlusRecordType,uint,uint,uchar const *,void *)

- ea: `0x180104bf0`
- end: `0x180104d61`
- name: `?AnalyzeMetafileForSpecialROPs@VectorImageResource@GEL@@CAHW4EmfPlusRecordType@Gdiplus@@IIPEBEPEAX@Z`
- size: `369`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18007f754`
- `0x180104bf0`
- `0x180104d64`
- `0x180105010`

## import_xrefs

- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180104d51`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180104d51`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180104d45`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180104d45`
- `GDI32!DeleteDC` at `0x180104d1a`
- `GDI32!DeleteDC` at `0x180104d1a`
- `GDI32!CreateCompatibleDC` at `0x180104cab`
- `GDI32!CreateCompatibleDC` at `0x180104cab`
- `gdiplus!GdipEnumerateMetafileDestPoint` at `0x180104d0c`
- `gdiplus!GdipEnumerateMetafileDestPoint` at `0x180104d0c`
- `gdiplus!GdipDeleteGraphics` at `0x180104d2b`
- `gdiplus!GdipDeleteGraphics` at `0x180104d2b`
- `gdiplus!GdipCreateFromHDC` at `0x180104cc9`
- `gdiplus!GdipCreateFromHDC` at `0x180104cc9`
- `gdiplus!GdipDisposeImage` at `0x180104c90`
- `gdiplus!GdipDisposeImage` at `0x180104c90`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall GEL::VectorImageResource::AnalyzeMetafileForSpecialROPs(
        unsigned int a1,
        __int16 a2,
        unsigned int a3,
        _DWORD *a4,
        struct GEL::MetafileRasterOpData *a5)
{
  struct GEL::MetafileRasterOpData *v6; // rbx
  struct GEL::MetafileRasterOpData *v7; // rcx
  HDC CompatibleDC; // rdi
  unsigned int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // [rsp+30h] [rbp-28h] BYREF
  _QWORD v13[4]; // [rsp+38h] [rbp-20h] BYREF

  if ( a1 != 16392 )
  {
    GEL::ITech::AnalyzeMetafileRecordForRasterOp(a5, a1, a4, a3);
    return 1;
  }
  if ( (a2 & 0x7F00) != 0x500 || a3 < 8 )
    return 1;
  if ( a4 )
  {
    if ( a4[1] == 2 )
    {
      v6 = a5;
      if ( !*((_BYTE *)a5 + 8) )
      {
        *((_BYTE *)a5 + 8) = 1;
        a5 = 0;
        GEL::CreateMetafileFromRecord(
          (GEL *)&a5,
          (struct Gdiplus::GpMetafile **)a3,
          (unsigned int)a4,
          (const unsigned __int8 *)a3);
        v7 = a5;
        if ( a5 )
        {
          v12 = 0;
          CompatibleDC = CreateCompatibleDC(0);
          v13[1] = CompatibleDC;
          v9 = GdipCreateFromHDC(CompatibleDC, &v12);
          try
          {
            Gfx::GdipStatus_ThrowOnFailureMessageTag(v9, v10, v11, 39081348);
            v13[0] = 0;
            GdipEnumerateMetafileDestPoint(
              v12,
              a5,
              v13,
              &GEL::VectorImageResource::AnalyzeMetafileForSpecialROPs,
              v6,
              0);
            if ( CompatibleDC )
              DeleteDC(CompatibleDC);
            if ( v12 )
              GdipDeleteGraphics();
            v7 = a5;
          }
          catch ( ... )
          {
            MsoShipAssertTagProc(2929249);
            return 0;
          }
        }
        if ( v7 )
          GdipDisposeImage();
        *((_BYTE *)v6 + 8) = 0;
      }
    }
    return 1;
  }
  MsoShipAssertTagProc(2929248);
  return 0;
}

```

## disassembly

```asm
0x180104bf0  mov     [rsp+arg_0], rbx
0x180104bf5  push    rdi
0x180104bf6  sub     rsp, 50h
0x180104bfa  mov     rax, r9
0x180104bfd  mov     r9d, r8d; unsigned __int8 *
0x180104c00  cmp     ecx, 4008h
0x180104c06  jz      short loc_180104C2A
0x180104c08  mov     r8, rax; void *
0x180104c0b  mov     edx, ecx; unsigned int
0x180104c0d  mov     rcx, [rsp+58h+arg_20]; struct GEL::MetafileRasterOpData *
0x180104c15  call    ?AnalyzeMetafileRecordForRasterOp@ITech@GEL@@SAXAEAUMetafileRasterOpData@2@KPEBXK@Z; GEL::ITech::AnalyzeMetafileRecordForRasterOp(GEL::MetafileRasterOpData &,ulong,void const *,ulong)
0x180104c1a  mov     eax, 1
0x180104c1f  mov     rbx, [rsp+58h+arg_0]
0x180104c24  add     rsp, 50h
0x180104c28  pop     rdi
0x180104c29  retn
0x180104c2a  and     edx, 7F00h
0x180104c30  cmp     edx, 500h
0x180104c36  jnz     short loc_180104C1A
0x180104c38  cmp     r9d, 8
0x180104c3c  jb      short loc_180104C1A
0x180104c3e  test    rax, rax
0x180104c41  jz      loc_180104D4C
0x180104c47  cmp     dword ptr [rax+4], 2
0x180104c4b  jnz     short loc_180104C1A
0x180104c4d  mov     rbx, [rsp+58h+arg_20]
0x180104c55  cmp     byte ptr [rbx+8], 0
0x180104c59  jnz     short loc_180104C1A
0x180104c5b  mov     byte ptr [rbx+8], 1
0x180104c5f  mov     [rsp+58h+arg_20], 0
0x180104c6b  mov     r8, rax; unsigned int
0x180104c6e  mov     edx, r9d; struct Gdiplus::GpMetafile **
0x180104c71  lea     rcx, [rsp+58h+arg_20]; this
0x180104c79  call    ?CreateMetafileFromRecord@GEL@@YAXPEAPEAVGpMetafile@Gdiplus@@IPEBE@Z; GEL::CreateMetafileFromRecord(Gdiplus::GpMetafile * *,uint,uchar const *)
0x180104c7e  mov     rcx, [rsp+58h+arg_20]
0x180104c86  test    rcx, rcx
0x180104c89  jnz     short loc_180104CA0
0x180104c8b  test    rcx, rcx
0x180104c8e  jz      short loc_180104C97
0x180104c90  call    cs:__imp_GdipDisposeImage
0x180104c96  nop
0x180104c97  mov     byte ptr [rbx+8], 0
0x180104c9b  jmp     loc_180104C1A
0x180104ca0  mov     [rsp+58h+var_28], 0
0x180104ca9  xor     ecx, ecx; hdc
0x180104cab  call    cs:__imp_CreateCompatibleDC
0x180104cb1  mov     rdi, rax
0x180104cb4  mov     [rsp+58h+var_18], rax
0x180104cb9  cmp     [rsp+58h+var_28], 0
0x180104cbf  jnz     short loc_180104D3E
0x180104cc1  lea     rdx, [rsp+58h+var_28]
0x180104cc6  mov     rcx, rax
0x180104cc9  call    cs:__imp_GdipCreateFromHDC
0x180104ccf  mov     r9d, 2545584h
0x180104cd5  mov     ecx, eax
0x180104cd7  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x180104cdc  mov     [rsp+58h+var_20], 0
0x180104ce5  mov     [rsp+58h+var_30], 0
0x180104cee  mov     [rsp+58h+var_38], rbx
0x180104cf3  lea     r9, ?AnalyzeMetafileForSpecialROPs@VectorImageResource@GEL@@CAHW4EmfPlusRecordType@Gdiplus@@IIPEBEPEAX@Z; GEL::VectorImageResource::AnalyzeMetafileForSpecialROPs(Gdiplus::EmfPlusRecordType,uint,uint,uchar const *,void *)
0x180104cfa  lea     r8, [rsp+58h+var_20]
0x180104cff  mov     rdx, [rsp+58h+arg_20]
0x180104d07  mov     rcx, [rsp+58h+var_28]
0x180104d0c  call    cs:__imp_GdipEnumerateMetafileDestPoint
0x180104d12  test    rdi, rdi
0x180104d15  jz      short loc_180104D21
0x180104d17  mov     rcx, rdi; hdc
0x180104d1a  call    cs:__imp_DeleteDC
0x180104d20  nop
0x180104d21  mov     rcx, [rsp+58h+var_28]
0x180104d26  test    rcx, rcx
0x180104d29  jz      short loc_180104D31
0x180104d2b  call    cs:__imp_GdipDeleteGraphics
0x180104d31  mov     rcx, [rsp+58h+arg_20]
0x180104d39  jmp     loc_180104C8B
0x180104d3e  xor     edx, edx
0x180104d40  mov     ecx, 1E55E058h
0x180104d45  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180104d4b  nop
0x180104d4c  mov     ecx, 2CB260h
0x180104d51  call    cs:__imp_MsoShipAssertTagProc
0x180104d57  jmp     short $+2
0x180104d59  xor     eax, eax
0x180104d5b  jmp     loc_180104C1F
```
