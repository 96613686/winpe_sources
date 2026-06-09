# Gfx::CreateImageFromHENHMETAFILE(HENHMETAFILE__ *)

- ea: `0x1800dba50`
- end: `0x1800dbb4c`
- name: `?CreateImageFromHENHMETAFILE@Gfx@@YA?AV?$TCntPtr@UIImage@GEL@@@Ofc@@PEAUHENHMETAFILE__@@@Z`
- size: `252`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops`

## callees

- `0x180020198`
- `0x180057e70`
- `0x180092a58`
- `0x1800dba50`
- `0x1800dbb50`
- `0x1800dbbb4`
- `0x1800dcec0`
- `0x1800dd460`

## import_xrefs

- `GDI32!GetEnhMetaFileBits` at `0x1800dba8d`
- `GDI32!GetEnhMetaFileBits` at `0x1800dbaac`
- `GDI32!GetEnhMetaFileBits` at `0x1800dba8d`
- `GDI32!GetEnhMetaFileBits` at `0x1800dbaac`
- `ole32!CreateStreamOnHGlobal` at `0x1800dba77`
- `ole32!CreateStreamOnHGlobal` at `0x1800dba77`

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
0x1800dba50  mov     [rsp+arg_0], rbx
0x1800dba55  push    rbp
0x1800dba56  push    rsi
0x1800dba57  push    rdi
0x1800dba58  sub     rsp, 40h
0x1800dba5c  mov     rbp, rdx
0x1800dba5f  mov     rdi, rcx
0x1800dba62  mov     [rsp+58h+ppstm], 0
0x1800dba6b  lea     r8, [rsp+58h+ppstm]; ppstm
0x1800dba70  mov     edx, 1; fDeleteOnRelease
0x1800dba75  xor     ecx, ecx; hGlobal
0x1800dba77  call    cs:__imp_CreateStreamOnHGlobal
0x1800dba7d  test    eax, eax
0x1800dba7f  js      loc_1800DBB24
0x1800dba85  xor     r8d, r8d; lpData
0x1800dba88  xor     edx, edx; nSize
0x1800dba8a  mov     rcx, rbp; hEMF
0x1800dba8d  call    cs:__imp_GetEnhMetaFileBits
0x1800dba93  mov     esi, eax
0x1800dba95  mov     ecx, eax; this
0x1800dba97  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1800dba9c  mov     rbx, rax
0x1800dba9f  mov     [rsp+58h+arg_18], rax
0x1800dbaa4  mov     r8, rax; lpData
0x1800dbaa7  mov     edx, esi; nSize
0x1800dbaa9  mov     rcx, rbp; hEMF
0x1800dbaac  call    cs:__imp_GetEnhMetaFileBits
0x1800dbab2  cmp     eax, esi
0x1800dbab4  jnz     loc_1800DBB41
0x1800dbaba  mov     rcx, [rsp+58h+ppstm]
0x1800dbabf  mov     rax, [rcx]
0x1800dbac2  xor     r9d, r9d
0x1800dbac5  mov     r8d, esi
0x1800dbac8  mov     rdx, rbx
0x1800dbacb  mov     rax, [rax+20h]
0x1800dbacf  call    cs:__guard_dispatch_icall_fptr
0x1800dbad5  test    eax, eax
0x1800dbad7  js      short loc_1800DBB41
0x1800dbad9  mov     rcx, [rsp+58h+ppstm]; this
0x1800dbade  call    ?RewindStream@Stream@Mso@@YAJAEAUIStream@@@Z; Mso::Stream::RewindStream(IStream &)
0x1800dbae3  test    eax, eax
0x1800dbae5  js      short loc_1800DBB34
0x1800dbae7  mov     rdx, [rsp+58h+ppstm]
0x1800dbaec  mov     rcx, rdi
0x1800dbaef  call    ?Create@IImage@GEL@@SA?AV?$TCntPtr@UIImage@GEL@@@Ofc@@PEAUIStream@@@Z; GEL::IImage::Create(IStream *)
0x1800dbaf4  nop
0x1800dbaf5  mov     rcx, rbx; void *
0x1800dbaf8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800dbafd  mov     rcx, [rsp+58h+ppstm]
0x1800dbb02  test    rcx, rcx
0x1800dbb05  jz      short loc_1800DBB14
0x1800dbb07  mov     rax, [rcx]
0x1800dbb0a  mov     rax, [rax+10h]
0x1800dbb0e  call    cs:__guard_dispatch_icall_fptr
0x1800dbb14  mov     rax, rdi
0x1800dbb17  mov     rbx, [rsp+58h+arg_0]
0x1800dbb1c  add     rsp, 40h
0x1800dbb20  pop     rdi
0x1800dbb21  pop     rsi
0x1800dbb22  pop     rbp
0x1800dbb23  retn
0x1800dbb24  mov     edx, 48C8DDh; unsigned int
0x1800dbb29  mov     ecx, eax; int
0x1800dbb2b  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x1800dbb30  nop
0x1800dbb31  jmp     short $+2
0x1800dbb33  nop
0x1800dbb34  mov     edx, 48C8DEh; unsigned int
0x1800dbb39  mov     ecx, eax; int
0x1800dbb3b  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x1800dbb40  int     3; Trap to Debugger
0x1800dbb41  mov     ecx, 859212h; unsigned int
0x1800dbb46  call    ?ThrowTag@FailureException@GEL@@SAXK@Z; GEL::FailureException::ThrowTag(ulong)
0x1800dbb4b  int     3; Trap to Debugger
```
