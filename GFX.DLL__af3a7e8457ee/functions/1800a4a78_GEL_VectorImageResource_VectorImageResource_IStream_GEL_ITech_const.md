# GEL::VectorImageResource::VectorImageResource(IStream *,GEL::ITech const *)

- ea: `0x1800a4a78`
- end: `0x1800a4e51`
- name: `??0VectorImageResource@GEL@@QEAA@PEAUIStream@@PEBUITech@1@@Z`
- size: `985`
- prototype: `__int64 __fastcall(GEL::VectorImageResource *__hidden this, struct IStream *, const struct GEL::ITech *)`
- caller_count: `3`
- callee_count: `14`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800a4a10`
- `0x1800b2bec`
- `0x180141444`

## callees

- `0x18001ffb4`
- `0x180055b26`
- `0x180056ee0`
- `0x1800573f0`
- `0x1800786fc`
- `0x1800a4a78`
- `0x1800a4e54`
- `0x1800a50f4`
- `0x1800a51e0`
- `0x1800a5a58`
- `0x1800a5bd0`
- `0x1800a5ca8`
- `0x18010e0bc`
- `0x18016ed84`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800a4cd8`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800a4e00`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800a4cd8`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800a4e00`
- `GDI32!SetMetaFileBitsEx` at `0x1800a4d90`
- `GDI32!SetMetaFileBitsEx` at `0x1800a4d90`
- `GDI32!DeleteMetaFile` at `0x1800a4e11`
- `GDI32!DeleteMetaFile` at `0x1800a4e11`
- `gdiplus!GdipLoadImageFromStreamICM` at `0x1800a4e3b`
- `gdiplus!GdipLoadImageFromStreamICM` at `0x1800a4e3b`
- `gdiplus!GdipGetMetafileHeaderFromStream` at `0x1800a4b8e`
- `gdiplus!GdipGetMetafileHeaderFromStream` at `0x1800a4b8e`
- `gdiplus!GdipCreateMetafileFromWmf` at `0x1800a4e27`
- `gdiplus!GdipCreateMetafileFromWmf` at `0x1800a4e27`
- `gdiplus!GdipDisposeImage` at `0x1800a4c84`
- `gdiplus!GdipDisposeImage` at `0x1800a4d4a`
- `gdiplus!GdipDisposeImage` at `0x1800a4c84`
- `gdiplus!GdipDisposeImage` at `0x1800a4d4a`
- `ole32!CoTaskMemFree` at `0x1800a4c67`
- `ole32!CoTaskMemFree` at `0x1800a4c67`

## string_xrefs

- `0x1800a4d26`: `VectorImageResource: Created image from IStream`

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
  unsigned int v10; // r8d
  unsigned int v11; // esi
  BYTE *v12; // rbx
  __int64 v13; // rbx
  bool v14; // zf
  HMETAFILE v16; // rsi
  HMETAFILE v17; // rcx
  const char *v18; // [rsp+30h] [rbp-D0h] BYREF
  UINT cbBuffer; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v20; // [rsp+40h] [rbp-C0h] BYREF
  struct tagRECT v21; // [rsp+48h] [rbp-B8h] BYREF
  GEL::VectorImageResource *v22; // [rsp+58h] [rbp-A8h]
  _BYTE v23[16]; // [rsp+60h] [rbp-A0h] BYREF
  float v24; // [rsp+70h] [rbp-90h]
  struct tagRECT v25; // [rsp+78h] [rbp-88h]
  __int128 v26; // [rsp+F0h] [rbp-10h] BYREF
  int v27; // [rsp+100h] [rbp+0h]
  __int16 v28; // [rsp+104h] [rbp+4h]
  LPVOID pv[2]; // [rsp+110h] [rbp+10h] BYREF
  Mso::Memory::Throw *v30; // [rsp+120h] [rbp+20h]

  v22 = this;
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
  v18 = 0;
  v20 = 0;
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
  memset_0(v23, 0, 0x8Cu);
  memset_0(pv, 0, 0x50u);
  MetafileHeaderFromStream = GdipGetMetafileHeaderFromStream(*((_QWORD *)this + 2), v23);
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
      if ( (unsigned __int64)v30 > 0xFFFFFFFF )
        goto LABEL_41;
      v11 = (unsigned int)v30;
      v12 = (BYTE *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)(unsigned int)v30, v9, v10);
      *(_QWORD *)&v21.left = v12;
      cbBuffer = 0;
      if ( (*(int (__fastcall **)(_QWORD, BYTE *, _QWORD, UINT *))(**((_QWORD **)this + 2) + 24LL))(
             *((_QWORD *)this + 2),
             v12,
             v11,
             &cbBuffer) < 0
        || !cbBuffer )
      {
        goto LABEL_13;
      }
      v16 = SetMetaFileBitsEx(cbBuffer, v12);
      v17 = (HMETAFILE)*((_QWORD *)this + 4);
      if ( v17 )
        DeleteMetaFile(v17);
      *((_QWORD *)this + 4) = v16;
      if ( v16 )
      {
        v26 = 0;
        v27 = 0;
        v28 = 0;
        v21 = v25;
        GEL::VectorImageResource::BuildPlaceableWMF((struct Gdiplus::WmfPlaceableFileHeader *)&v26, &v21, (int)v24);
        if ( v20 )
        {
          CrashWithRecovery(0x1E55E058u, 0);
LABEL_41:
          safeint_exception_handlers::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
        }
        MetafileHeaderFromStream = GdipCreateMetafileFromWmf(v16, 0, &v26, &v20);
      }
      else
      {
LABEL_13:
        MetafileHeaderFromStream = 1;
      }
      operator delete(v12);
    }
  }
  if ( pv[0] )
    CoTaskMemFree(pv[0]);
  if ( MetafileHeaderFromStream )
  {
LABEL_24:
    if ( (*(int (__fastcall **)(_QWORD, const char *, _QWORD, _QWORD))(**((_QWORD **)this + 2) + 40LL))(
           *((_QWORD *)this + 2),
           v18,
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
          || (v14 = !GEL::VectorImageResource::ImportWIC(this, *((struct IStream **)this + 2)), v7 = 0, !v14) )
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
    v13 = v20;
    v20 = 0;
    if ( *v4 )
      GdipDisposeImage();
    *v4 = v13;
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
  v18 = "VectorImageResource: Created image from IStream";
  GEL::VectorImageResource::SendImageLogging(this, &v18);
  if ( v20 )
    GdipDisposeImage();
  return this;
}

```

## disassembly

```asm
0x1800a4a78  mov     [rsp-8+arg_8], rbx
0x1800a4a7d  mov     [rsp-8+arg_10], rsi
0x1800a4a82  push    rbp
0x1800a4a83  push    r12
0x1800a4a85  push    r13
0x1800a4a87  push    r14
0x1800a4a89  push    r15
0x1800a4a8b  lea     rbp, [rsp-70h]
0x1800a4a90  sub     rsp, 170h
0x1800a4a97  mov     rax, cs:__security_cookie
0x1800a4a9e  xor     rax, rsp
0x1800a4aa1  mov     [rbp+90h+var_30], rax
0x1800a4aa5  mov     r14, rcx
0x1800a4aa8  mov     [rsp+190h+var_138], rcx
0x1800a4aad  lea     rax, ??_7VectorImageResource@GEL@@6B@; const GEL::VectorImageResource::`vftable'
0x1800a4ab4  mov     [rcx], rax
0x1800a4ab7  lea     r12, [rcx+8]
0x1800a4abb  xor     r13d, r13d
0x1800a4abe  mov     [r12], r13
0x1800a4ac2  mov     [rcx+10h], rdx
0x1800a4ac6  test    rdx, rdx
0x1800a4ac9  jz      short loc_1800A4ADC
0x1800a4acb  mov     rax, [rdx]
0x1800a4ace  mov     rcx, rdx
0x1800a4ad1  mov     rax, [rax+8]
0x1800a4ad5  call    cs:__guard_dispatch_icall_fptr
0x1800a4adb  nop
0x1800a4adc  mov     [r14+18h], r13
0x1800a4ae0  mov     [r14+20h], r13
0x1800a4ae4  mov     [r14+28h], r13w
0x1800a4ae9  mov     r15d, 1
0x1800a4aef  mov     [r14+2Ah], r15b
0x1800a4af3  mov     [r14+30h], r13
0x1800a4af7  mov     [r14+38h], r13
0x1800a4afb  mov     [r14+40h], r13
0x1800a4aff  mov     [r14+48h], r13
0x1800a4b03  mov     byte ptr [r14+50h], 2
0x1800a4b08  mov     dword ptr [r14+54h], 0FFFFFFFFh
0x1800a4b10  add     cs:?s_activeVectors@VectorResourceTally@GEL@@0GA, r15w; ushort GEL::VectorResourceTally::s_activeVectors
0x1800a4b18  mov     [r14+5Ch], r13
0x1800a4b1c  mov     [r14+64h], r13d
0x1800a4b20  mov     dword ptr [r14+68h], 10000h
0x1800a4b28  mov     [r14+6Ch], r13b
0x1800a4b2c  mov     [rsp+190h+var_160], r13
0x1800a4b31  mov     [rsp+190h+var_150], r13
0x1800a4b36  mov     rcx, [r14+10h]
0x1800a4b3a  mov     al, r13b
0x1800a4b3d  test    rcx, rcx
0x1800a4b40  jz      loc_1800A4D0E
0x1800a4b46  mov     rax, [rcx]
0x1800a4b49  xor     r9d, r9d
0x1800a4b4c  xor     r8d, r8d
0x1800a4b4f  mov     rdx, r13
0x1800a4b52  mov     rax, [rax+28h]
0x1800a4b56  call    cs:__guard_dispatch_icall_fptr
0x1800a4b5c  test    eax, eax
0x1800a4b5e  js      loc_1800A4CA3
0x1800a4b64  xor     edx, edx; Val
0x1800a4b66  mov     r8d, 8Ch; Size
0x1800a4b6c  lea     rcx, [rsp+190h+var_130]; void *
0x1800a4b71  call    memset_0
0x1800a4b76  xor     edx, edx; Val
0x1800a4b78  lea     r8d, [r15+4Fh]; Size
0x1800a4b7c  lea     rcx, [rbp+90h+pv]; void *
0x1800a4b80  call    memset_0
0x1800a4b85  lea     rdx, [rsp+190h+var_130]
0x1800a4b8a  mov     rcx, [r14+10h]
0x1800a4b8e  call    cs:__imp_GdipGetMetafileHeaderFromStream
0x1800a4b94  mov     esi, eax
0x1800a4b96  mov     rcx, [r14+10h]
0x1800a4b9a  mov     rax, [rcx]
0x1800a4b9d  xor     r9d, r9d
0x1800a4ba0  xor     r8d, r8d
0x1800a4ba3  mov     rdx, r13
0x1800a4ba6  mov     rax, [rax+28h]
0x1800a4baa  call    cs:__guard_dispatch_icall_fptr
0x1800a4bb0  test    eax, eax
0x1800a4bb2  cmovs   esi, r15d
0x1800a4bb6  test    esi, esi
0x1800a4bb8  jnz     loc_1800A4C5E
0x1800a4bbe  mov     rcx, [r14+10h]
0x1800a4bc2  mov     rax, [rcx]
0x1800a4bc5  xor     r8d, r8d
0x1800a4bc8  lea     rdx, [rbp+90h+pv]
0x1800a4bcc  mov     rax, [rax+60h]
0x1800a4bd0  call    cs:__guard_dispatch_icall_fptr
0x1800a4bd6  test    eax, eax
0x1800a4bd8  js      loc_1800A4C5E
0x1800a4bde  mov     rcx, [r14+10h]
0x1800a4be2  mov     rax, [rcx]
0x1800a4be5  xor     r9d, r9d
0x1800a4be8  xor     r8d, r8d
0x1800a4beb  mov     rdx, r13
0x1800a4bee  mov     rax, [rax+28h]
0x1800a4bf2  call    cs:__guard_dispatch_icall_fptr
0x1800a4bf8  test    eax, eax
0x1800a4bfa  js      loc_1800A4D85
0x1800a4c00  mov     eax, 0FFFFFFFFh
0x1800a4c05  cmp     [rbp+90h+var_70], rax
0x1800a4c09  ja      loc_1800A4E07
0x1800a4c0f  mov     esi, dword ptr [rbp+90h+var_70]
0x1800a4c12  mov     ecx, esi; this
0x1800a4c14  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1800a4c19  mov     rbx, rax
0x1800a4c1c  mov     qword ptr [rsp+190h+var_148.left], rax
0x1800a4c21  mov     [rsp+190h+cbBuffer], r13d
0x1800a4c26  mov     rcx, [r14+10h]
0x1800a4c2a  mov     rax, [rcx]
0x1800a4c2d  lea     r9, [rsp+190h+cbBuffer]
0x1800a4c32  mov     r8d, esi
0x1800a4c35  mov     rdx, rbx
0x1800a4c38  mov     rax, [rax+18h]
0x1800a4c3c  call    cs:__guard_dispatch_icall_fptr
0x1800a4c42  test    eax, eax
0x1800a4c44  js      short loc_1800A4C52
0x1800a4c46  mov     ecx, [rsp+190h+cbBuffer]; cbBuffer
0x1800a4c4a  test    ecx, ecx
0x1800a4c4c  jnz     loc_1800A4D8D
0x1800a4c52  mov     esi, r15d
0x1800a4c55  mov     rcx, rbx; void *
0x1800a4c58  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800a4c5d  nop
0x1800a4c5e  mov     rcx, [rbp+90h+pv]; pv
0x1800a4c62  test    rcx, rcx
0x1800a4c65  jz      short loc_1800A4C6D
0x1800a4c67  call    cs:__imp_CoTaskMemFree
0x1800a4c6d  test    esi, esi
0x1800a4c6f  jnz     short loc_1800A4CA3
0x1800a4c71  mov     rbx, [rsp+190h+var_150]
0x1800a4c76  mov     [rsp+190h+var_150], r13
0x1800a4c7b  mov     rcx, [r12]
0x1800a4c7f  test    rcx, rcx
0x1800a4c82  jz      short loc_1800A4C8A
0x1800a4c84  call    cs:__imp_GdipDisposeImage
0x1800a4c8a  mov     [r12], rbx
0x1800a4c8e  test    esi, esi
0x1800a4c90  jnz     short loc_1800A4CDF
0x1800a4c92  mov     rcx, r14; this
0x1800a4c95  call    ?HasValidTypeAndDimensions@VectorImageResource@GEL@@AEAA_NXZ; GEL::VectorImageResource::HasValidTypeAndDimensions(void)
0x1800a4c9a  test    al, al
0x1800a4c9c  jz      short loc_1800A4D12
0x1800a4c9e  mov     r15b, r13b
0x1800a4ca1  jmp     short loc_1800A4D12
0x1800a4ca3  mov     rcx, [r14+10h]
0x1800a4ca7  mov     rax, [rcx]
0x1800a4caa  xor     r9d, r9d
0x1800a4cad  xor     r8d, r8d
0x1800a4cb0  mov     rdx, [rsp+190h+var_160]
0x1800a4cb5  mov     rax, [rax+28h]
0x1800a4cb9  call    cs:__guard_dispatch_icall_fptr
0x1800a4cbf  test    eax, eax
0x1800a4cc1  js      loc_1800A4D7D
0x1800a4cc7  cmp     [r12], r13
0x1800a4ccb  jz      loc_1800A4E34
0x1800a4cd1  xor     edx, edx
0x1800a4cd3  mov     ecx, 1E55E058h
0x1800a4cd8  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800a4cde  nop
0x1800a4cdf  mov     rdx, [r14+10h]; struct IStream *
0x1800a4ce3  mov     rcx, r14; this
0x1800a4ce6  call    ?Import@VectorImageResource@GEL@@AEAA_NPEAUIStream@@@Z; GEL::VectorImageResource::Import(IStream *)
0x1800a4ceb  test    al, al
0x1800a4ced  jnz     loc_1800A4E48
0x1800a4cf3  mov     rdx, [r14+10h]; struct IStream *
0x1800a4cf7  mov     rcx, r14; this
0x1800a4cfa  call    ?ImportWIC@VectorImageResource@GEL@@AEAA_NPEAUIStream@@@Z; GEL::VectorImageResource::ImportWIC(IStream *)
0x1800a4cff  test    al, al
0x1800a4d01  mov     al, r13b
0x1800a4d04  jnz     loc_1800A4E48
0x1800a4d0a  mov     [r14+6Bh], al
0x1800a4d0e  test    al, al
0x1800a4d10  jnz     short loc_1800A4C92
0x1800a4d12  mov     [r14+6Ah], r15b
0x1800a4d16  mov     rcx, r14; this
0x1800a4d19  call    ?ProcessMetafile@VectorImageResource@GEL@@AEAAXXZ; GEL::VectorImageResource::ProcessMetafile(void)
0x1800a4d1e  mov     rcx, r14; this
0x1800a4d21  call    ?StoreDPI@VectorImageResource@GEL@@AEAAXXZ; GEL::VectorImageResource::StoreDPI(void)
0x1800a4d26  lea     rax, aVectorimageres; "VectorImageResource: Created image from"...
0x1800a4d2d  mov     [rsp+190h+var_160], rax
0x1800a4d32  lea     rdx, [rsp+190h+var_160]
0x1800a4d37  mov     rcx, r14
0x1800a4d3a  call    ?SendImageLogging@VectorImageResource@GEL@@AEAAXAEBV?$StringLiteral@D@StringLiterals@Mso@@@Z; GEL::VectorImageResource::SendImageLogging(Mso::StringLiterals::StringLiteral<char> const &)
0x1800a4d3f  nop
0x1800a4d40  mov     rcx, [rsp+190h+var_150]
0x1800a4d45  test    rcx, rcx
0x1800a4d48  jz      short loc_1800A4D51
0x1800a4d4a  call    cs:__imp_GdipDisposeImage
0x1800a4d50  nop
0x1800a4d51  mov     rax, r14
0x1800a4d54  mov     rcx, [rbp+90h+var_30]
0x1800a4d58  xor     rcx, rsp; StackCookie
0x1800a4d5b  call    __security_check_cookie
0x1800a4d60  lea     r11, [rsp+190h+var_20]
0x1800a4d68  mov     rbx, [r11+38h]
0x1800a4d6c  mov     rsi, [r11+40h]
0x1800a4d70  mov     rsp, r11
0x1800a4d73  pop     r15
0x1800a4d75  pop     r14
0x1800a4d77  pop     r13
0x1800a4d79  pop     r12
0x1800a4d7b  pop     rbp
0x1800a4d7c  retn
0x1800a4d7d  mov     esi, r15d
0x1800a4d80  jmp     loc_1800A4C8E
0x1800a4d85  mov     esi, r15d
0x1800a4d88  jmp     loc_1800A4C5E
0x1800a4d8d  mov     rdx, rbx; lpData
0x1800a4d90  call    cs:__imp_SetMetaFileBitsEx
0x1800a4d96  mov     rsi, rax
0x1800a4d99  mov     rcx, [r14+20h]; hmf
0x1800a4d9d  test    rcx, rcx
0x1800a4da0  jnz     short loc_1800A4E11
0x1800a4da2  mov     [r14+20h], rsi
0x1800a4da6  test    rsi, rsi
0x1800a4da9  jz      loc_1800A4C52
0x1800a4daf  xorps   xmm0, xmm0
0x1800a4db2  xor     eax, eax
0x1800a4db4  movups  [rbp+90h+var_A0], xmm0
0x1800a4db8  mov     [rbp+90h+var_90], eax
0x1800a4dbb  mov     [rbp+90h+var_8C], ax
0x1800a4dbf  mov     eax, [rsp+190h+var_118]
0x1800a4dc3  mov     [rsp+190h+var_148.left], eax
0x1800a4dc7  mov     eax, [rsp+190h+var_114]
0x1800a4dcb  mov     [rsp+190h+var_148.top], eax
0x1800a4dcf  mov     eax, [rbp+90h+var_110]
0x1800a4dd2  mov     [rsp+190h+var_148.right], eax
0x1800a4dd6  mov     eax, [rbp+90h+var_10C]
0x1800a4dd9  mov     [rsp+190h+var_148.bottom], eax
0x1800a4ddd  cvttss2si r8d, [rsp+190h+var_120]; int
0x1800a4de4  lea     rdx, [rsp+190h+var_148]; struct tagRECT *
0x1800a4de9  lea     rcx, [rbp+90h+var_A0]; struct Gdiplus::WmfPlaceableFileHeader *
0x1800a4ded  call    ?BuildPlaceableWMF@VectorImageResource@GEL@@CAXAEAUWmfPlaceableFileHeader@Gdiplus@@AEBUtagRECT@@H@Z; GEL::VectorImageResource::BuildPlaceableWMF(Gdiplus::WmfPlaceableFileHeader &,tagRECT const &,int)
0x1800a4df2  cmp     [rsp+190h+var_150], r13
0x1800a4df7  jz      short loc_1800A4E19
0x1800a4df9  xor     edx, edx
0x1800a4dfb  mov     ecx, 1E55E058h
0x1800a4e00  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800a4e06  nop
0x1800a4e07  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@safeint_exception_handlers@@SAXXZ; safeint_exception_handlers::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x1800a4e11  call    cs:__imp_DeleteMetaFile
0x1800a4e17  jmp     short loc_1800A4DA2
0x1800a4e19  lea     r9, [rsp+190h+var_150]
0x1800a4e1e  lea     r8, [rbp+90h+var_A0]
0x1800a4e22  xor     edx, edx
0x1800a4e24  mov     rcx, rsi
0x1800a4e27  call    cs:__imp_GdipCreateMetafileFromWmf
0x1800a4e2d  mov     esi, eax
0x1800a4e2f  jmp     loc_1800A4C55
0x1800a4e34  mov     rdx, r12
0x1800a4e37  mov     rcx, [r14+10h]
0x1800a4e3b  call    cs:__imp_GdipLoadImageFromStreamICM
0x1800a4e41  mov     esi, eax
0x1800a4e43  jmp     loc_1800A4C8E
0x1800a4e48  mov     al, r15b
0x1800a4e4b  jmp     loc_1800A4D0A
```
