# GEL::VectorImageResource::VectorImageResource(IStream *,GEL::ITech const *)

- ea: `0x1800e39c8`
- end: `0x1800e3da1`
- name: `??0VectorImageResource@GEL@@QEAA@PEAUIStream@@PEBUITech@1@@Z`
- size: `985`
- prototype: `__int64 __fastcall(GEL::VectorImageResource *__hidden this, struct IStream *, const struct GEL::ITech *)`
- caller_count: `3`
- callee_count: `14`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800ba2ec`
- `0x1800e3960`
- `0x1800ecc44`

## callees

- `0x180020198`
- `0x1800565ba`
- `0x1800578b0`
- `0x180057e70`
- `0x180092a58`
- `0x1800c0700`
- `0x1800e39c8`
- `0x1800e3da4`
- `0x1800e4040`
- `0x1800e4128`
- `0x1800e4968`
- `0x1800e4d84`
- `0x1800e4e5c`
- `0x180172ff4`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800e3c28`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800e3d50`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800e3c28`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800e3d50`
- `GDI32!SetMetaFileBitsEx` at `0x1800e3ce0`
- `GDI32!SetMetaFileBitsEx` at `0x1800e3ce0`
- `GDI32!DeleteMetaFile` at `0x1800e3d61`
- `GDI32!DeleteMetaFile` at `0x1800e3d61`
- `gdiplus!GdipLoadImageFromStreamICM` at `0x1800e3d8b`
- `gdiplus!GdipLoadImageFromStreamICM` at `0x1800e3d8b`
- `gdiplus!GdipGetMetafileHeaderFromStream` at `0x1800e3ade`
- `gdiplus!GdipGetMetafileHeaderFromStream` at `0x1800e3ade`
- `gdiplus!GdipCreateMetafileFromWmf` at `0x1800e3d77`
- `gdiplus!GdipCreateMetafileFromWmf` at `0x1800e3d77`
- `gdiplus!GdipDisposeImage` at `0x1800e3bd4`
- `gdiplus!GdipDisposeImage` at `0x1800e3c9a`
- `gdiplus!GdipDisposeImage` at `0x1800e3bd4`
- `gdiplus!GdipDisposeImage` at `0x1800e3c9a`
- `ole32!CoTaskMemFree` at `0x1800e3bb7`
- `ole32!CoTaskMemFree` at `0x1800e3bb7`

## string_xrefs

- `0x1800e3c76`: `VectorImageResource: Created image from IStream`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
GEL::VectorImageResource *__fastcall GEL::VectorImageResource::VectorImageResource(
        GEL::VectorImageResource *this,
        struct IStream *a2,
        const struct GEL::ITech *a3)
{
  _QWORD *v4; // r12
  char v5; // r15
  __int64 v6; // rcx
  char v7; // al
  int MetafileHeaderFromStream; // esi
  unsigned __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  unsigned int v13; // esi
  BYTE *v14; // rbx
  __int64 v15; // rbx
  bool v16; // zf
  HMETAFILE v18; // rsi
  HMETAFILE v19; // rcx
  const char *v20; // [rsp+30h] [rbp-D0h] BYREF
  UINT cbBuffer; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v22; // [rsp+40h] [rbp-C0h] BYREF
  struct tagRECT v23; // [rsp+48h] [rbp-B8h] BYREF
  GEL::VectorImageResource *v24; // [rsp+58h] [rbp-A8h]
  _BYTE v25[16]; // [rsp+60h] [rbp-A0h] BYREF
  float v26; // [rsp+70h] [rbp-90h]
  struct tagRECT v27; // [rsp+78h] [rbp-88h]
  __int128 v28; // [rsp+F0h] [rbp-10h] BYREF
  int v29; // [rsp+100h] [rbp+0h]
  __int16 v30; // [rsp+104h] [rbp+4h]
  LPVOID pv[2]; // [rsp+110h] [rbp+10h] BYREF
  Mso::Memory::Throw *v32; // [rsp+120h] [rbp+20h]

  v24 = this;
  *(_QWORD *)this = &GEL::VectorImageResource::`vftable';
  v4 = (_QWORD *)((char *)this + 8);
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = a2;
  if ( a2 )
    ((void (__fastcall *)(struct IStream *))a2->lpVtbl->AddRef)(a2);
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_WORD *)this + 20) = 0;
  v5 = 1;
  *((_BYTE *)this + 42) = 1;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_BYTE *)this + 80) = 2;
  *((_DWORD *)this + 21) = -1;
  ++GEL::VectorResourceTally::s_activeVectors;
  *(_QWORD *)((char *)this + 92) = 0;
  *((_DWORD *)this + 25) = 0;
  *((_DWORD *)this + 26) = 0x10000;
  *((_BYTE *)this + 108) = 0;
  v20 = 0;
  v22 = 0;
  v6 = *((_QWORD *)this + 2);
  v7 = 0;
  if ( !v6 )
  {
LABEL_30:
    if ( !v7 )
      goto LABEL_31;
    goto LABEL_22;
  }
  if ( (*(int (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v6 + 40LL))(v6, 0, 0, 0) < 0 )
    goto LABEL_24;
  memset_0(v25, 0, 0x8Cu);
  memset_0(pv, 0, 0x50u);
  MetafileHeaderFromStream = GdipGetMetafileHeaderFromStream(*((_QWORD *)this + 2), v25);
  if ( (*(int (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 2) + 40LL))(
         *((_QWORD *)this + 2),
         0,
         0,
         0) < 0 )
    MetafileHeaderFromStream = 1;
  if ( !MetafileHeaderFromStream
    && (*(int (__fastcall **)(_QWORD, LPVOID *, _QWORD))(**((_QWORD **)this + 2) + 96LL))(*((_QWORD *)this + 2), pv, 0) >= 0 )
  {
    if ( (*(int (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 2) + 40LL))(
           *((_QWORD *)this + 2),
           0,
           0,
           0) < 0 )
    {
      MetafileHeaderFromStream = 1;
    }
    else
    {
      if ( (unsigned __int64)v32 > 0xFFFFFFFF )
        goto LABEL_41;
      v13 = (unsigned int)v32;
      v14 = (BYTE *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)(unsigned int)v32, v9, v11);
      *(_QWORD *)&v23.left = v14;
      cbBuffer = 0;
      if ( (*(int (__fastcall **)(_QWORD, BYTE *, _QWORD, UINT *))(**((_QWORD **)this + 2) + 24LL))(
             *((_QWORD *)this + 2),
             v14,
             v13,
             &cbBuffer) < 0
        || !cbBuffer )
      {
        goto LABEL_13;
      }
      v18 = SetMetaFileBitsEx(cbBuffer, v14);
      v19 = (HMETAFILE)*((_QWORD *)this + 4);
      if ( v19 )
        DeleteMetaFile(v19);
      *((_QWORD *)this + 4) = v18;
      if ( v18 )
      {
        v28 = 0;
        v29 = 0;
        v30 = 0;
        v23 = v27;
        GEL::VectorImageResource::BuildPlaceableWMF((struct Gdiplus::WmfPlaceableFileHeader *)&v28, &v23, (int)v26);
        if ( v22 )
        {
          CrashWithRecovery(0x1E55E058u, 0);
LABEL_41:
          safeint_exception_handlers::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v10, v9, v11, v12);
        }
        MetafileHeaderFromStream = GdipCreateMetafileFromWmf(v18, 0, &v28, &v22);
      }
      else
      {
LABEL_13:
        MetafileHeaderFromStream = 1;
      }
      operator delete(v14);
    }
  }
  if ( pv[0] )
    CoTaskMemFree(pv[0]);
  if ( MetafileHeaderFromStream )
  {
LABEL_24:
    if ( (*(int (__fastcall **)(_QWORD, const char *, _QWORD, _QWORD))(**((_QWORD **)this + 2) + 40LL))(
           *((_QWORD *)this + 2),
           v20,
           0,
           0) < 0 )
    {
      MetafileHeaderFromStream = 1;
    }
    else
    {
      if ( *v4 )
      {
        CrashWithRecovery(0x1E55E058u, 0);
LABEL_27:
        if ( GEL::VectorImageResource::Import(this, *((struct IStream **)this + 2))
          || (v16 = !GEL::VectorImageResource::ImportWIC(this, *((struct IStream **)this + 2)), v7 = 0, !v16) )
        {
          v7 = 1;
        }
        *((_BYTE *)this + 107) = v7;
        goto LABEL_30;
      }
      MetafileHeaderFromStream = GdipLoadImageFromStreamICM(*((_QWORD *)this + 2), v4);
    }
  }
  else
  {
    v15 = v22;
    v22 = 0;
    if ( *v4 )
      GdipDisposeImage();
    *v4 = v15;
  }
  if ( MetafileHeaderFromStream )
    goto LABEL_27;
LABEL_22:
  if ( GEL::VectorImageResource::HasValidTypeAndDimensions(this) )
    v5 = 0;
LABEL_31:
  *((_BYTE *)this + 106) = v5;
  GEL::VectorImageResource::ProcessMetafile(this);
  GEL::VectorImageResource::StoreDPI(this);
  v20 = "VectorImageResource: Created image from IStream";
  GEL::VectorImageResource::SendImageLogging(this, &v20);
  if ( v22 )
    GdipDisposeImage();
  return this;
}

```

## disassembly

```asm
0x1800e39c8  mov     [rsp-8+arg_8], rbx
0x1800e39cd  mov     [rsp-8+arg_10], rsi
0x1800e39d2  push    rbp
0x1800e39d3  push    r12
0x1800e39d5  push    r13
0x1800e39d7  push    r14
0x1800e39d9  push    r15
0x1800e39db  lea     rbp, [rsp-70h]
0x1800e39e0  sub     rsp, 170h
0x1800e39e7  mov     rax, cs:__security_cookie
0x1800e39ee  xor     rax, rsp
0x1800e39f1  mov     [rbp+90h+var_30], rax
0x1800e39f5  mov     r14, rcx
0x1800e39f8  mov     [rsp+190h+var_138], rcx
0x1800e39fd  lea     rax, ??_7VectorImageResource@GEL@@6B@; const GEL::VectorImageResource::`vftable'
0x1800e3a04  mov     [rcx], rax
0x1800e3a07  lea     r12, [rcx+8]
0x1800e3a0b  xor     r13d, r13d
0x1800e3a0e  mov     [r12], r13
0x1800e3a12  mov     [rcx+10h], rdx
0x1800e3a16  test    rdx, rdx
0x1800e3a19  jz      short loc_1800E3A2C
0x1800e3a1b  mov     rax, [rdx]
0x1800e3a1e  mov     rcx, rdx
0x1800e3a21  mov     rax, [rax+8]
0x1800e3a25  call    cs:__guard_dispatch_icall_fptr
0x1800e3a2b  nop
0x1800e3a2c  mov     [r14+18h], r13
0x1800e3a30  mov     [r14+20h], r13
0x1800e3a34  mov     [r14+28h], r13w
0x1800e3a39  mov     r15d, 1
0x1800e3a3f  mov     [r14+2Ah], r15b
0x1800e3a43  mov     [r14+30h], r13
0x1800e3a47  mov     [r14+38h], r13
0x1800e3a4b  mov     [r14+40h], r13
0x1800e3a4f  mov     [r14+48h], r13
0x1800e3a53  mov     byte ptr [r14+50h], 2
0x1800e3a58  mov     dword ptr [r14+54h], 0FFFFFFFFh
0x1800e3a60  add     cs:?s_activeVectors@VectorResourceTally@GEL@@0GA, r15w; ushort GEL::VectorResourceTally::s_activeVectors
0x1800e3a68  mov     [r14+5Ch], r13
0x1800e3a6c  mov     [r14+64h], r13d
0x1800e3a70  mov     dword ptr [r14+68h], 10000h
0x1800e3a78  mov     [r14+6Ch], r13b
0x1800e3a7c  mov     [rsp+190h+var_160], r13
0x1800e3a81  mov     [rsp+190h+var_150], r13
0x1800e3a86  mov     rcx, [r14+10h]
0x1800e3a8a  mov     al, r13b
0x1800e3a8d  test    rcx, rcx
0x1800e3a90  jz      loc_1800E3C5E
0x1800e3a96  mov     rax, [rcx]
0x1800e3a99  xor     r9d, r9d
0x1800e3a9c  xor     r8d, r8d
0x1800e3a9f  mov     rdx, r13
0x1800e3aa2  mov     rax, [rax+28h]
0x1800e3aa6  call    cs:__guard_dispatch_icall_fptr
0x1800e3aac  test    eax, eax
0x1800e3aae  js      loc_1800E3BF3
0x1800e3ab4  xor     edx, edx; Val
0x1800e3ab6  mov     r8d, 8Ch; Size
0x1800e3abc  lea     rcx, [rsp+190h+var_130]; void *
0x1800e3ac1  call    memset_0
0x1800e3ac6  xor     edx, edx; Val
0x1800e3ac8  lea     r8d, [r15+4Fh]; Size
0x1800e3acc  lea     rcx, [rbp+90h+pv]; void *
0x1800e3ad0  call    memset_0
0x1800e3ad5  lea     rdx, [rsp+190h+var_130]
0x1800e3ada  mov     rcx, [r14+10h]
0x1800e3ade  call    cs:__imp_GdipGetMetafileHeaderFromStream
0x1800e3ae4  mov     esi, eax
0x1800e3ae6  mov     rcx, [r14+10h]
0x1800e3aea  mov     rax, [rcx]
0x1800e3aed  xor     r9d, r9d
0x1800e3af0  xor     r8d, r8d
0x1800e3af3  mov     rdx, r13
0x1800e3af6  mov     rax, [rax+28h]
0x1800e3afa  call    cs:__guard_dispatch_icall_fptr
0x1800e3b00  test    eax, eax
0x1800e3b02  cmovs   esi, r15d
0x1800e3b06  test    esi, esi
0x1800e3b08  jnz     loc_1800E3BAE
0x1800e3b0e  mov     rcx, [r14+10h]
0x1800e3b12  mov     rax, [rcx]
0x1800e3b15  xor     r8d, r8d
0x1800e3b18  lea     rdx, [rbp+90h+pv]
0x1800e3b1c  mov     rax, [rax+60h]
0x1800e3b20  call    cs:__guard_dispatch_icall_fptr
0x1800e3b26  test    eax, eax
0x1800e3b28  js      loc_1800E3BAE
0x1800e3b2e  mov     rcx, [r14+10h]
0x1800e3b32  mov     rax, [rcx]
0x1800e3b35  xor     r9d, r9d
0x1800e3b38  xor     r8d, r8d
0x1800e3b3b  mov     rdx, r13
0x1800e3b3e  mov     rax, [rax+28h]
0x1800e3b42  call    cs:__guard_dispatch_icall_fptr
0x1800e3b48  test    eax, eax
0x1800e3b4a  js      loc_1800E3CD5
0x1800e3b50  mov     eax, 0FFFFFFFFh
0x1800e3b55  cmp     [rbp+90h+var_70], rax
0x1800e3b59  ja      loc_1800E3D57
0x1800e3b5f  mov     esi, dword ptr [rbp+90h+var_70]
0x1800e3b62  mov     ecx, esi; this
0x1800e3b64  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1800e3b69  mov     rbx, rax
0x1800e3b6c  mov     qword ptr [rsp+190h+var_148.left], rax
0x1800e3b71  mov     [rsp+190h+cbBuffer], r13d
0x1800e3b76  mov     rcx, [r14+10h]
0x1800e3b7a  mov     rax, [rcx]
0x1800e3b7d  lea     r9, [rsp+190h+cbBuffer]
0x1800e3b82  mov     r8d, esi
0x1800e3b85  mov     rdx, rbx
0x1800e3b88  mov     rax, [rax+18h]
0x1800e3b8c  call    cs:__guard_dispatch_icall_fptr
0x1800e3b92  test    eax, eax
0x1800e3b94  js      short loc_1800E3BA2
0x1800e3b96  mov     ecx, [rsp+190h+cbBuffer]; cbBuffer
0x1800e3b9a  test    ecx, ecx
0x1800e3b9c  jnz     loc_1800E3CDD
0x1800e3ba2  mov     esi, r15d
0x1800e3ba5  mov     rcx, rbx; void *
0x1800e3ba8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800e3bad  nop
0x1800e3bae  mov     rcx, [rbp+90h+pv]; pv
0x1800e3bb2  test    rcx, rcx
0x1800e3bb5  jz      short loc_1800E3BBD
0x1800e3bb7  call    cs:__imp_CoTaskMemFree
0x1800e3bbd  test    esi, esi
0x1800e3bbf  jnz     short loc_1800E3BF3
0x1800e3bc1  mov     rbx, [rsp+190h+var_150]
0x1800e3bc6  mov     [rsp+190h+var_150], r13
0x1800e3bcb  mov     rcx, [r12]
0x1800e3bcf  test    rcx, rcx
0x1800e3bd2  jz      short loc_1800E3BDA
0x1800e3bd4  call    cs:__imp_GdipDisposeImage
0x1800e3bda  mov     [r12], rbx
0x1800e3bde  test    esi, esi
0x1800e3be0  jnz     short loc_1800E3C2F
0x1800e3be2  mov     rcx, r14; this
0x1800e3be5  call    ?HasValidTypeAndDimensions@VectorImageResource@GEL@@AEAA_NXZ; GEL::VectorImageResource::HasValidTypeAndDimensions(void)
0x1800e3bea  test    al, al
0x1800e3bec  jz      short loc_1800E3C62
0x1800e3bee  mov     r15b, r13b
0x1800e3bf1  jmp     short loc_1800E3C62
0x1800e3bf3  mov     rcx, [r14+10h]
0x1800e3bf7  mov     rax, [rcx]
0x1800e3bfa  xor     r9d, r9d
0x1800e3bfd  xor     r8d, r8d
0x1800e3c00  mov     rdx, [rsp+190h+var_160]
0x1800e3c05  mov     rax, [rax+28h]
0x1800e3c09  call    cs:__guard_dispatch_icall_fptr
0x1800e3c0f  test    eax, eax
0x1800e3c11  js      loc_1800E3CCD
0x1800e3c17  cmp     [r12], r13
0x1800e3c1b  jz      loc_1800E3D84
0x1800e3c21  xor     edx, edx
0x1800e3c23  mov     ecx, 1E55E058h
0x1800e3c28  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800e3c2e  nop
0x1800e3c2f  mov     rdx, [r14+10h]; struct IStream *
0x1800e3c33  mov     rcx, r14; this
0x1800e3c36  call    ?Import@VectorImageResource@GEL@@AEAA_NPEAUIStream@@@Z; GEL::VectorImageResource::Import(IStream *)
0x1800e3c3b  test    al, al
0x1800e3c3d  jnz     loc_1800E3D98
0x1800e3c43  mov     rdx, [r14+10h]; struct IStream *
0x1800e3c47  mov     rcx, r14; this
0x1800e3c4a  call    ?ImportWIC@VectorImageResource@GEL@@AEAA_NPEAUIStream@@@Z; GEL::VectorImageResource::ImportWIC(IStream *)
0x1800e3c4f  test    al, al
0x1800e3c51  mov     al, r13b
0x1800e3c54  jnz     loc_1800E3D98
0x1800e3c5a  mov     [r14+6Bh], al
0x1800e3c5e  test    al, al
0x1800e3c60  jnz     short loc_1800E3BE2
0x1800e3c62  mov     [r14+6Ah], r15b
0x1800e3c66  mov     rcx, r14; this
0x1800e3c69  call    ?ProcessMetafile@VectorImageResource@GEL@@AEAAXXZ; GEL::VectorImageResource::ProcessMetafile(void)
0x1800e3c6e  mov     rcx, r14; this
0x1800e3c71  call    ?StoreDPI@VectorImageResource@GEL@@AEAAXXZ; GEL::VectorImageResource::StoreDPI(void)
0x1800e3c76  lea     rax, aVectorimageres; "VectorImageResource: Created image from"...
0x1800e3c7d  mov     [rsp+190h+var_160], rax
0x1800e3c82  lea     rdx, [rsp+190h+var_160]
0x1800e3c87  mov     rcx, r14
0x1800e3c8a  call    ?SendImageLogging@VectorImageResource@GEL@@AEAAXAEBV?$StringLiteral@D@StringLiterals@Mso@@@Z; GEL::VectorImageResource::SendImageLogging(Mso::StringLiterals::StringLiteral<char> const &)
0x1800e3c8f  nop
0x1800e3c90  mov     rcx, [rsp+190h+var_150]
0x1800e3c95  test    rcx, rcx
0x1800e3c98  jz      short loc_1800E3CA1
0x1800e3c9a  call    cs:__imp_GdipDisposeImage
0x1800e3ca0  nop
0x1800e3ca1  mov     rax, r14
0x1800e3ca4  mov     rcx, [rbp+90h+var_30]
0x1800e3ca8  xor     rcx, rsp; StackCookie
0x1800e3cab  call    __security_check_cookie
0x1800e3cb0  lea     r11, [rsp+190h+var_20]
0x1800e3cb8  mov     rbx, [r11+38h]
0x1800e3cbc  mov     rsi, [r11+40h]
0x1800e3cc0  mov     rsp, r11
0x1800e3cc3  pop     r15
0x1800e3cc5  pop     r14
0x1800e3cc7  pop     r13
0x1800e3cc9  pop     r12
0x1800e3ccb  pop     rbp
0x1800e3ccc  retn
0x1800e3ccd  mov     esi, r15d
0x1800e3cd0  jmp     loc_1800E3BDE
0x1800e3cd5  mov     esi, r15d
0x1800e3cd8  jmp     loc_1800E3BAE
0x1800e3cdd  mov     rdx, rbx; lpData
0x1800e3ce0  call    cs:__imp_SetMetaFileBitsEx
0x1800e3ce6  mov     rsi, rax
0x1800e3ce9  mov     rcx, [r14+20h]; hmf
0x1800e3ced  test    rcx, rcx
0x1800e3cf0  jnz     short loc_1800E3D61
0x1800e3cf2  mov     [r14+20h], rsi
0x1800e3cf6  test    rsi, rsi
0x1800e3cf9  jz      loc_1800E3BA2
0x1800e3cff  xorps   xmm0, xmm0
0x1800e3d02  xor     eax, eax
0x1800e3d04  movups  [rbp+90h+var_A0], xmm0
0x1800e3d08  mov     [rbp+90h+var_90], eax
0x1800e3d0b  mov     [rbp+90h+var_8C], ax
0x1800e3d0f  mov     eax, [rsp+190h+var_118]
0x1800e3d13  mov     [rsp+190h+var_148.left], eax
0x1800e3d17  mov     eax, [rsp+190h+var_114]
0x1800e3d1b  mov     [rsp+190h+var_148.top], eax
0x1800e3d1f  mov     eax, [rbp+90h+var_110]
0x1800e3d22  mov     [rsp+190h+var_148.right], eax
0x1800e3d26  mov     eax, [rbp+90h+var_10C]
0x1800e3d29  mov     [rsp+190h+var_148.bottom], eax
0x1800e3d2d  cvttss2si r8d, [rsp+190h+var_120]; int
0x1800e3d34  lea     rdx, [rsp+190h+var_148]; struct tagRECT *
0x1800e3d39  lea     rcx, [rbp+90h+var_A0]; struct Gdiplus::WmfPlaceableFileHeader *
0x1800e3d3d  call    ?BuildPlaceableWMF@VectorImageResource@GEL@@CAXAEAUWmfPlaceableFileHeader@Gdiplus@@AEBUtagRECT@@H@Z; GEL::VectorImageResource::BuildPlaceableWMF(Gdiplus::WmfPlaceableFileHeader &,tagRECT const &,int)
0x1800e3d42  cmp     [rsp+190h+var_150], r13
0x1800e3d47  jz      short loc_1800E3D69
0x1800e3d49  xor     edx, edx
0x1800e3d4b  mov     ecx, 1E55E058h
0x1800e3d50  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800e3d56  nop
0x1800e3d57  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@safeint_exception_handlers@@SAXXZ; safeint_exception_handlers::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x1800e3d61  call    cs:__imp_DeleteMetaFile
0x1800e3d67  jmp     short loc_1800E3CF2
0x1800e3d69  lea     r9, [rsp+190h+var_150]
0x1800e3d6e  lea     r8, [rbp+90h+var_A0]
0x1800e3d72  xor     edx, edx
0x1800e3d74  mov     rcx, rsi
0x1800e3d77  call    cs:__imp_GdipCreateMetafileFromWmf
0x1800e3d7d  mov     esi, eax
0x1800e3d7f  jmp     loc_1800E3BA5
0x1800e3d84  mov     rdx, r12
0x1800e3d87  mov     rcx, [r14+10h]
0x1800e3d8b  call    cs:__imp_GdipLoadImageFromStreamICM
0x1800e3d91  mov     esi, eax
0x1800e3d93  jmp     loc_1800E3BDE
0x1800e3d98  mov     al, r15b
0x1800e3d9b  jmp     loc_1800E3C5A
```
