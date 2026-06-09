# GEL::VectorImageResource::AnalyzeMetafileForSpecialROPs(Gdiplus::EmfPlusRecordType,uint,uint,uchar const *,void *)

- ea: `0x1801107c0`
- end: `0x180110932`
- name: `?AnalyzeMetafileForSpecialROPs@VectorImageResource@GEL@@CAHW4EmfPlusRecordType@Gdiplus@@IIPEBEPEAX@Z`
- size: `370`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180062394`
- `0x1801107c0`
- `0x180110934`
- `0x180110be0`

## import_xrefs

- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180110922`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180110922`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180110898`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180110898`
- `GDI32!DeleteDC` at `0x1801108f8`
- `GDI32!DeleteDC` at `0x1801108f8`
- `GDI32!CreateCompatibleDC` at `0x18011087b`
- `GDI32!CreateCompatibleDC` at `0x18011087b`
- `gdiplus!GdipEnumerateMetafileDestPoint` at `0x1801108ea`
- `gdiplus!GdipEnumerateMetafileDestPoint` at `0x1801108ea`
- `gdiplus!GdipDeleteGraphics` at `0x18011090a`
- `gdiplus!GdipDeleteGraphics` at `0x18011090a`
- `gdiplus!GdipCreateFromHDC` at `0x1801108a7`
- `gdiplus!GdipCreateFromHDC` at `0x1801108a7`
- `gdiplus!GdipDisposeImage` at `0x180110860`
- `gdiplus!GdipDisposeImage` at `0x180110860`

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
0x1801107c0  mov     [rsp+arg_0], rbx
0x1801107c5  push    rdi
0x1801107c6  sub     rsp, 50h
0x1801107ca  mov     rax, r9
0x1801107cd  mov     r9d, r8d; unsigned __int8 *
0x1801107d0  cmp     ecx, 4008h
0x1801107d6  jz      short loc_1801107FA
0x1801107d8  mov     r8, rax; void *
0x1801107db  mov     edx, ecx; unsigned int
0x1801107dd  mov     rcx, [rsp+58h+arg_20]; struct GEL::MetafileRasterOpData *
0x1801107e5  call    ?AnalyzeMetafileRecordForRasterOp@ITech@GEL@@SAXAEAUMetafileRasterOpData@2@KPEBXK@Z; GEL::ITech::AnalyzeMetafileRecordForRasterOp(GEL::MetafileRasterOpData &,ulong,void const *,ulong)
0x1801107ea  mov     eax, 1
0x1801107ef  mov     rbx, [rsp+58h+arg_0]
0x1801107f4  add     rsp, 50h
0x1801107f8  pop     rdi
0x1801107f9  retn
0x1801107fa  and     edx, 7F00h
0x180110800  cmp     edx, 500h
0x180110806  jnz     short loc_1801107EA
0x180110808  cmp     r9d, 8
0x18011080c  jb      short loc_1801107EA
0x18011080e  test    rax, rax
0x180110811  jz      loc_18011091D
0x180110817  cmp     dword ptr [rax+4], 2
0x18011081b  jnz     short loc_1801107EA
0x18011081d  mov     rbx, [rsp+58h+arg_20]
0x180110825  cmp     byte ptr [rbx+8], 0
0x180110829  jnz     short loc_1801107EA
0x18011082b  mov     byte ptr [rbx+8], 1
0x18011082f  mov     [rsp+58h+arg_20], 0
0x18011083b  mov     r8, rax; unsigned int
0x18011083e  mov     edx, r9d; struct Gdiplus::GpMetafile **
0x180110841  lea     rcx, [rsp+58h+arg_20]; this
0x180110849  call    ?CreateMetafileFromRecord@GEL@@YAXPEAPEAVGpMetafile@Gdiplus@@IPEBE@Z; GEL::CreateMetafileFromRecord(Gdiplus::GpMetafile * *,uint,uchar const *)
0x18011084e  mov     rcx, [rsp+58h+arg_20]
0x180110856  test    rcx, rcx
0x180110859  jnz     short loc_180110870
0x18011085b  test    rcx, rcx
0x18011085e  jz      short loc_180110867
0x180110860  call    cs:__imp_GdipDisposeImage
0x180110866  nop
0x180110867  mov     byte ptr [rbx+8], 0
0x18011086b  jmp     loc_1801107EA
0x180110870  mov     [rsp+58h+var_28], 0
0x180110879  xor     ecx, ecx; hdc
0x18011087b  call    cs:__imp_CreateCompatibleDC
0x180110881  mov     rdi, rax
0x180110884  mov     [rsp+58h+var_18], rax
0x180110889  cmp     [rsp+58h+var_28], 0
0x18011088f  jz      short loc_18011089F
0x180110891  xor     edx, edx
0x180110893  mov     ecx, 1E55E058h
0x180110898  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18011089e  nop
0x18011089f  lea     rdx, [rsp+58h+var_28]
0x1801108a4  mov     rcx, rdi
0x1801108a7  call    cs:__imp_GdipCreateFromHDC
0x1801108ad  mov     r9d, 2545584h
0x1801108b3  mov     ecx, eax
0x1801108b5  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1801108ba  mov     [rsp+58h+var_20], 0
0x1801108c3  mov     [rsp+58h+var_30], 0
0x1801108cc  mov     [rsp+58h+var_38], rbx
0x1801108d1  lea     r9, ?AnalyzeMetafileForSpecialROPs@VectorImageResource@GEL@@CAHW4EmfPlusRecordType@Gdiplus@@IIPEBEPEAX@Z; GEL::VectorImageResource::AnalyzeMetafileForSpecialROPs(Gdiplus::EmfPlusRecordType,uint,uint,uchar const *,void *)
0x1801108d8  lea     r8, [rsp+58h+var_20]
0x1801108dd  mov     rdx, [rsp+58h+arg_20]
0x1801108e5  mov     rcx, [rsp+58h+var_28]
0x1801108ea  call    cs:__imp_GdipEnumerateMetafileDestPoint
0x1801108f0  test    rdi, rdi
0x1801108f3  jz      short loc_180110900
0x1801108f5  mov     rcx, rdi; hdc
0x1801108f8  call    cs:__imp_DeleteDC
0x1801108fe  nop
0x1801108ff  nop
0x180110900  mov     rcx, [rsp+58h+var_28]
0x180110905  test    rcx, rcx
0x180110908  jz      short loc_180110910
0x18011090a  call    cs:__imp_GdipDeleteGraphics
0x180110910  mov     rcx, [rsp+58h+arg_20]
0x180110918  jmp     loc_18011085B
0x18011091d  mov     ecx, 2CB260h
0x180110922  call    cs:__imp_MsoShipAssertTagProc
0x180110928  jmp     short $+2
0x18011092a  xor     eax, eax
0x18011092c  jmp     loc_1801107EF
```
