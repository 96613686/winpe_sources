# GEL::GDIPathResource::GDIPathResource(GEL::IPath const &)

- ea: `0x1801cd9e8`
- end: `0x1801cdb6a`
- name: `??0GDIPathResource@GEL@@QEAA@AEBUIPath@1@@Z`
- size: `386`
- prototype: `__int64 __fastcall(GEL::GDIPathResource *__hidden this, const struct GEL::IPath *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1801ce7c8`

## callees

- `0x180057e70`
- `0x18007f754`
- `0x18007fb74`
- `0x1801cd9e8`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801cda6a`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801cda6a`
- `gdiplus!GdipAddPathPath` at `0x1801cdb2a`
- `gdiplus!GdipAddPathPath` at `0x1801cdb2a`
- `gdiplus!GdipDeletePath` at `0x1801cdb47`
- `gdiplus!GdipDeletePath` at `0x1801cdb47`
- `gdiplus!GdipCreatePath` at `0x1801cda77`
- `gdiplus!GdipCreatePath` at `0x1801cda77`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
GEL::GDIPathResource *__fastcall GEL::GDIPathResource::GDIPathResource(
        GEL::GDIPathResource *this,
        const struct GEL::IPath *a2)
{
  _QWORD *v4; // r15
  unsigned int v5; // r12d
  unsigned int Path; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  unsigned int i; // ebx
  __int64 v10; // rsi
  unsigned int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v15; // [rsp+20h] [rbp-10h] BYREF
  int v16; // [rsp+78h] [rbp+48h] BYREF
  int v17; // [rsp+80h] [rbp+50h] BYREF
  __int64 v18; // [rsp+88h] [rbp+58h] BYREF

  *(_OWORD *)this = 0;
  *((_OWORD *)this + 1) = 0;
  *((_DWORD *)this + 2) = 0;
  *((_DWORD *)this + 8) = 1;
  *(_QWORD *)this = &GEL::GDIPathResource::`vftable'{for `Mso::TRefCountedImpl<Mso::IRefCounted>'};
  *((_QWORD *)this + 2) = &GEL::EffectColorBlend::`vftable'{for `Cache::IResourceState'};
  *((_QWORD *)this + 3) = &GEL::Arc2DRadialPathGradientBrushResource::`vftable'{for `ICacheResourceStateProvider'};
  v4 = (_QWORD *)((char *)this + 40);
  *((_QWORD *)this + 5) = 0;
  v5 = (*(__int64 (__fastcall **)(const struct GEL::IPath *))(*(_QWORD *)a2 + 200LL))(a2);
  if ( *v4 )
    CrashWithRecovery(0x1E55E058u, 0);
  Path = GdipCreatePath(v5, v4);
  Gfx::GdipStatus_ThrowOnFailureMessageTag(Path, v7, v8, 39081158);
  v16 = 0;
  v17 = 0;
  (*(void (__fastcall **)(const struct GEL::IPath *, int *, int *))(*(_QWORD *)a2 + 184LL))(a2, &v16, &v17);
  for ( i = 0; (int)i < v16; ++i )
  {
    v10 = *(_QWORD *)(*(__int64 (__fastcall **)(const struct GEL::IPath *, __int64 *, _QWORD))(*(_QWORD *)a2 + 248LL))(
                       a2,
                       &v15,
                       i);
    if ( v15 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
    if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v10 + 24LL))(v10) )
    {
      v18 = 0;
      if ( (unsigned __int8)sub_18007FB74(v10, v5, &v18) )
      {
        v11 = GdipAddPathPath(*v4, v18, 0);
        Gfx::GdipStatus_ThrowOnFailureMessageTag(v11, v12, v13, 39081159);
      }
      if ( v18 )
        GdipDeletePath();
    }
  }
  return this;
}

```

## disassembly

```asm
0x1801cd9e8  mov     [rsp-38h+arg_0], rcx
0x1801cd9ed  push    rbp
0x1801cd9ee  push    rbx
0x1801cd9ef  push    rsi
0x1801cd9f0  push    rdi
0x1801cd9f1  push    r12
0x1801cd9f3  push    r14
0x1801cd9f5  push    r15
0x1801cd9f7  mov     rbp, rsp
0x1801cd9fa  sub     rsp, 30h
0x1801cd9fe  mov     r14, rdx
0x1801cda01  mov     rdi, rcx
0x1801cda04  xorps   xmm0, xmm0
0x1801cda07  movups  xmmword ptr [rcx], xmm0
0x1801cda0a  movups  xmmword ptr [rcx+10h], xmm0
0x1801cda0e  mov     dword ptr [rcx+8], 0
0x1801cda15  mov     dword ptr [rcx+20h], 1
0x1801cda1c  lea     rax, ??_7GDIPathResource@GEL@@6B?$TRefCountedImpl@UIRefCounted@Mso@@@Mso@@@; const GEL::GDIPathResource::`vftable'{for `Mso::TRefCountedImpl<Mso::IRefCounted>'}
0x1801cda23  mov     [rcx], rax
0x1801cda26  lea     rax, ??_7EffectColorBlend@GEL@@6BIResourceState@Cache@@@; const GEL::EffectColorBlend::`vftable'{for `Cache::IResourceState'}
0x1801cda2d  mov     [rcx+10h], rax
0x1801cda31  lea     rax, ??_7Arc2DRadialPathGradientBrushResource@GEL@@6BICacheResourceStateProvider@@@; const GEL::Arc2DRadialPathGradientBrushResource::`vftable'{for `ICacheResourceStateProvider'}
0x1801cda38  mov     [rcx+18h], rax
0x1801cda3c  lea     r15, [rcx+28h]
0x1801cda40  mov     qword ptr [r15], 0
0x1801cda47  mov     rax, [rdx]
0x1801cda4a  mov     rcx, rdx
0x1801cda4d  mov     rax, [rax+0C8h]
0x1801cda54  call    cs:__guard_dispatch_icall_fptr
0x1801cda5a  mov     r12d, eax
0x1801cda5d  cmp     qword ptr [r15], 0
0x1801cda61  jz      short loc_1801CDA71
0x1801cda63  xor     edx, edx
0x1801cda65  mov     ecx, 1E55E058h
0x1801cda6a  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1801cda70  nop
0x1801cda71  mov     rdx, r15
0x1801cda74  mov     ecx, r12d
0x1801cda77  call    cs:__imp_GdipCreatePath
0x1801cda7d  mov     r9d, 25454C6h
0x1801cda83  mov     ecx, eax
0x1801cda85  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1801cda8a  mov     [rbp+arg_8], 0
0x1801cda91  mov     [rbp+arg_10], 0
0x1801cda98  mov     rax, [r14]
0x1801cda9b  lea     r8, [rbp+arg_10]
0x1801cda9f  lea     rdx, [rbp+arg_8]
0x1801cdaa3  mov     rcx, r14
0x1801cdaa6  mov     rax, [rax+0B8h]
0x1801cdaad  call    cs:__guard_dispatch_icall_fptr
0x1801cdab3  xor     ebx, ebx
0x1801cdab5  cmp     [rbp+arg_8], ebx
0x1801cdab8  jle     loc_1801CDB58
0x1801cdabe  mov     rax, [r14]
0x1801cdac1  mov     r8d, ebx
0x1801cdac4  lea     rdx, [rbp+var_10]
0x1801cdac8  mov     rcx, r14
0x1801cdacb  mov     rax, [rax+0F8h]
0x1801cdad2  call    cs:__guard_dispatch_icall_fptr
0x1801cdad8  mov     rsi, [rax]
0x1801cdadb  mov     rcx, [rbp+var_10]
0x1801cdadf  test    rcx, rcx
0x1801cdae2  jz      short loc_1801CDAF1
0x1801cdae4  mov     rax, [rcx]
0x1801cdae7  mov     rax, [rax+8]
0x1801cdaeb  call    cs:__guard_dispatch_icall_fptr
0x1801cdaf1  mov     rax, [rsi]
0x1801cdaf4  mov     rcx, rsi
0x1801cdaf7  mov     rax, [rax+18h]
0x1801cdafb  call    cs:__guard_dispatch_icall_fptr
0x1801cdb01  test    al, al
0x1801cdb03  jnz     short loc_1801CDB4D
0x1801cdb05  mov     [rbp+arg_18], 0
0x1801cdb0d  lea     r8, [rbp+arg_18]
0x1801cdb11  mov     edx, r12d
0x1801cdb14  mov     rcx, rsi
0x1801cdb17  call    sub_18007FB74
0x1801cdb1c  test    al, al
0x1801cdb1e  jz      short loc_1801CDB3E
0x1801cdb20  xor     r8d, r8d
0x1801cdb23  mov     rdx, [rbp+arg_18]
0x1801cdb27  mov     rcx, [r15]
0x1801cdb2a  call    cs:__imp_GdipAddPathPath
0x1801cdb30  mov     r9d, 25454C7h
0x1801cdb36  mov     ecx, eax
0x1801cdb38  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1801cdb3d  nop
0x1801cdb3e  mov     rcx, [rbp+arg_18]
0x1801cdb42  test    rcx, rcx
0x1801cdb45  jz      short loc_1801CDB4D
0x1801cdb47  call    cs:__imp_GdipDeletePath
0x1801cdb4d  inc     ebx
0x1801cdb4f  cmp     ebx, [rbp+arg_8]
0x1801cdb52  jl      loc_1801CDABE
0x1801cdb58  mov     rax, rdi
0x1801cdb5b  add     rsp, 30h
0x1801cdb5f  pop     r15
0x1801cdb61  pop     r14
0x1801cdb63  pop     r12
0x1801cdb65  pop     rdi
0x1801cdb66  pop     rsi
0x1801cdb67  pop     rbx
0x1801cdb68  pop     rbp
0x1801cdb69  retn
```
