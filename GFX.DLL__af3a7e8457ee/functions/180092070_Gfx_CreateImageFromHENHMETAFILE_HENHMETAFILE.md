# Gfx::CreateImageFromHENHMETAFILE(HENHMETAFILE__ *)

- ea: `0x180092070`
- end: `0x18009216c`
- name: `?CreateImageFromHENHMETAFILE@Gfx@@YA?AV?$TCntPtr@UIImage@GEL@@@Ofc@@PEAUHENHMETAFILE__@@@Z`
- size: `252`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops`

## callees

- `0x18001ffb4`
- `0x1800573f0`
- `0x1800786fc`
- `0x180092070`
- `0x180092460`
- `0x1800928c4`
- `0x1800a9b44`
- `0x1800d33a4`

## import_xrefs

- `GDI32!GetEnhMetaFileBits` at `0x1800920ad`
- `GDI32!GetEnhMetaFileBits` at `0x1800920cc`
- `GDI32!GetEnhMetaFileBits` at `0x1800920ad`
- `GDI32!GetEnhMetaFileBits` at `0x1800920cc`
- `ole32!CreateStreamOnHGlobal` at `0x180092097`
- `ole32!CreateStreamOnHGlobal` at `0x180092097`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Gfx::CreateImageFromHENHMETAFILE(__int64 a1, HENHMETAFILE a2)
{
  HRESULT v4; // eax
  Mso::Memory::Throw *EnhMetaFileBits; // rsi
  unsigned __int64 v6; // rdx
  unsigned int v7; // r8d
  BYTE *v8; // rbx
  struct IStream *v9; // rdx
  int v10; // eax
  LPSTREAM ppstm; // [rsp+70h] [rbp+18h] BYREF
  BYTE *v13; // [rsp+78h] [rbp+20h]

  ppstm = 0;
  v4 = CreateStreamOnHGlobal(0, 1, &ppstm);
  if ( v4 < 0 )
  {
    Ofc::CHResultException::ThrowTag(v4, 0x48C8DDu);
    goto LABEL_9;
  }
  EnhMetaFileBits = (Mso::Memory::Throw *)GetEnhMetaFileBits(a2, 0, 0);
  v8 = (BYTE *)Mso::Memory::Throw::AllocateEx(EnhMetaFileBits, v6, v7);
  v13 = v8;
  if ( GetEnhMetaFileBits(a2, (UINT)EnhMetaFileBits, v8) != (_DWORD)EnhMetaFileBits
    || ((int (__fastcall *)(LPSTREAM, BYTE *, _QWORD, _QWORD))ppstm->lpVtbl->Write)(
         ppstm,
         v8,
         (unsigned int)EnhMetaFileBits,
         0) < 0 )
  {
    GEL::FailureException::ThrowTag(0x859212u);
    __debugbreak();
  }
  v10 = Mso::Stream::RewindStream((Mso::Stream *)ppstm, v9);
  if ( v10 < 0 )
  {
LABEL_9:
    Ofc::CHResultException::ThrowTag(v10, 0x48C8DEu);
    __debugbreak();
  }
  GEL::IImage::Create(a1, ppstm);
  operator delete(v8);
  if ( ppstm )
    ((void (__fastcall *)(LPSTREAM))ppstm->lpVtbl->Release)(ppstm);
  return a1;
}

```

## disassembly

```asm
0x180092070  mov     [rsp+arg_0], rbx
0x180092075  push    rbp
0x180092076  push    rsi
0x180092077  push    rdi
0x180092078  sub     rsp, 40h
0x18009207c  mov     rbp, rdx
0x18009207f  mov     rdi, rcx
0x180092082  mov     [rsp+58h+ppstm], 0
0x18009208b  lea     r8, [rsp+58h+ppstm]; ppstm
0x180092090  mov     edx, 1; fDeleteOnRelease
0x180092095  xor     ecx, ecx; hGlobal
0x180092097  call    cs:__imp_CreateStreamOnHGlobal
0x18009209d  test    eax, eax
0x18009209f  js      loc_180092144
0x1800920a5  xor     r8d, r8d; lpData
0x1800920a8  xor     edx, edx; nSize
0x1800920aa  mov     rcx, rbp; hEMF
0x1800920ad  call    cs:__imp_GetEnhMetaFileBits
0x1800920b3  mov     esi, eax
0x1800920b5  mov     ecx, eax; this
0x1800920b7  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1800920bc  mov     rbx, rax
0x1800920bf  mov     [rsp+58h+arg_18], rax
0x1800920c4  mov     r8, rax; lpData
0x1800920c7  mov     edx, esi; nSize
0x1800920c9  mov     rcx, rbp; hEMF
0x1800920cc  call    cs:__imp_GetEnhMetaFileBits
0x1800920d2  cmp     eax, esi
0x1800920d4  jnz     loc_180092161
0x1800920da  mov     rcx, [rsp+58h+ppstm]
0x1800920df  mov     rax, [rcx]
0x1800920e2  xor     r9d, r9d
0x1800920e5  mov     r8d, esi
0x1800920e8  mov     rdx, rbx
0x1800920eb  mov     rax, [rax+20h]
0x1800920ef  call    cs:__guard_dispatch_icall_fptr
0x1800920f5  test    eax, eax
0x1800920f7  js      short loc_180092161
0x1800920f9  mov     rcx, [rsp+58h+ppstm]; this
0x1800920fe  call    ?RewindStream@Stream@Mso@@YAJAEAUIStream@@@Z; Mso::Stream::RewindStream(IStream &)
0x180092103  test    eax, eax
0x180092105  js      short loc_180092154
0x180092107  mov     rdx, [rsp+58h+ppstm]
0x18009210c  mov     rcx, rdi
0x18009210f  call    ?Create@IImage@GEL@@SA?AV?$TCntPtr@UIImage@GEL@@@Ofc@@PEAUIStream@@@Z; GEL::IImage::Create(IStream *)
0x180092114  nop
0x180092115  mov     rcx, rbx; void *
0x180092118  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18009211d  mov     rcx, [rsp+58h+ppstm]
0x180092122  test    rcx, rcx
0x180092125  jz      short loc_180092134
0x180092127  mov     rax, [rcx]
0x18009212a  mov     rax, [rax+10h]
0x18009212e  call    cs:__guard_dispatch_icall_fptr
0x180092134  mov     rax, rdi
0x180092137  mov     rbx, [rsp+58h+arg_0]
0x18009213c  add     rsp, 40h
0x180092140  pop     rdi
0x180092141  pop     rsi
0x180092142  pop     rbp
0x180092143  retn
0x180092144  mov     edx, 48C8DDh; unsigned int
0x180092149  mov     ecx, eax; int
0x18009214b  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x180092150  nop
0x180092151  jmp     short $+2
0x180092153  nop
0x180092154  mov     edx, 48C8DEh; unsigned int
0x180092159  mov     ecx, eax; int
0x18009215b  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x180092160  int     3; Trap to Debugger
0x180092161  mov     ecx, 859212h; unsigned int
0x180092166  call    ?ThrowTag@FailureException@GEL@@SAXK@Z; GEL::FailureException::ThrowTag(ulong)
0x18009216b  int     3; Trap to Debugger
```
