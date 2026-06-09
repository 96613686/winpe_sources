# GEL::GDIPathResource::GDIPathResource(GEL::IPath const &)

- ea: `0x1801c8d48`
- end: `0x1801c8eca`
- name: `??0GDIPathResource@GEL@@QEAA@AEBUIPath@1@@Z`
- size: `386`
- prototype: `__int64 __fastcall(GEL::GDIPathResource *__hidden this, const struct GEL::IPath *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1801c9b28`

## callees

- `0x1800573f0`
- `0x180061960`
- `0x180062394`
- `0x1801c8d48`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801c8dca`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801c8dca`
- `gdiplus!GdipAddPathPath` at `0x1801c8e8a`
- `gdiplus!GdipAddPathPath` at `0x1801c8e8a`
- `gdiplus!GdipDeletePath` at `0x1801c8ea7`
- `gdiplus!GdipDeletePath` at `0x1801c8ea7`
- `gdiplus!GdipCreatePath` at `0x1801c8dd7`
- `gdiplus!GdipCreatePath` at `0x1801c8dd7`

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
      if ( (unsigned __int8)sub_180061960(v10, v5, &v18) )
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
0x1801c8d48  mov     [rsp-38h+arg_0], rcx
0x1801c8d4d  push    rbp
0x1801c8d4e  push    rbx
0x1801c8d4f  push    rsi
0x1801c8d50  push    rdi
0x1801c8d51  push    r12
0x1801c8d53  push    r14
0x1801c8d55  push    r15
0x1801c8d57  mov     rbp, rsp
0x1801c8d5a  sub     rsp, 30h
0x1801c8d5e  mov     r14, rdx
0x1801c8d61  mov     rdi, rcx
0x1801c8d64  xorps   xmm0, xmm0
0x1801c8d67  movups  xmmword ptr [rcx], xmm0
0x1801c8d6a  movups  xmmword ptr [rcx+10h], xmm0
0x1801c8d6e  mov     dword ptr [rcx+8], 0
0x1801c8d75  mov     dword ptr [rcx+20h], 1
0x1801c8d7c  lea     rax, ??_7GDIPathResource@GEL@@6B?$TRefCountedImpl@UIRefCounted@Mso@@@Mso@@@; const GEL::GDIPathResource::`vftable'{for `Mso::TRefCountedImpl<Mso::IRefCounted>'}
0x1801c8d83  mov     [rcx], rax
0x1801c8d86  lea     rax, ??_7EffectColorBlend@GEL@@6BIResourceState@Cache@@@; const GEL::EffectColorBlend::`vftable'{for `Cache::IResourceState'}
0x1801c8d8d  mov     [rcx+10h], rax
0x1801c8d91  lea     rax, ??_7Arc2DRadialPathGradientBrushResource@GEL@@6BICacheResourceStateProvider@@@; const GEL::Arc2DRadialPathGradientBrushResource::`vftable'{for `ICacheResourceStateProvider'}
0x1801c8d98  mov     [rcx+18h], rax
0x1801c8d9c  lea     r15, [rcx+28h]
0x1801c8da0  mov     qword ptr [r15], 0
0x1801c8da7  mov     rax, [rdx]
0x1801c8daa  mov     rcx, rdx
0x1801c8dad  mov     rax, [rax+0C8h]
0x1801c8db4  call    cs:__guard_dispatch_icall_fptr
0x1801c8dba  mov     r12d, eax
0x1801c8dbd  cmp     qword ptr [r15], 0
0x1801c8dc1  jz      short loc_1801C8DD1
0x1801c8dc3  xor     edx, edx
0x1801c8dc5  mov     ecx, 1E55E058h
0x1801c8dca  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1801c8dd0  nop
0x1801c8dd1  mov     rdx, r15
0x1801c8dd4  mov     ecx, r12d
0x1801c8dd7  call    cs:__imp_GdipCreatePath
0x1801c8ddd  mov     r9d, 25454C6h
0x1801c8de3  mov     ecx, eax
0x1801c8de5  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1801c8dea  mov     [rbp+arg_8], 0
0x1801c8df1  mov     [rbp+arg_10], 0
0x1801c8df8  mov     rax, [r14]
0x1801c8dfb  lea     r8, [rbp+arg_10]
0x1801c8dff  lea     rdx, [rbp+arg_8]
0x1801c8e03  mov     rcx, r14
0x1801c8e06  mov     rax, [rax+0B8h]
0x1801c8e0d  call    cs:__guard_dispatch_icall_fptr
0x1801c8e13  xor     ebx, ebx
0x1801c8e15  cmp     [rbp+arg_8], ebx
0x1801c8e18  jle     loc_1801C8EB8
0x1801c8e1e  mov     rax, [r14]
0x1801c8e21  mov     r8d, ebx
0x1801c8e24  lea     rdx, [rbp+var_10]
0x1801c8e28  mov     rcx, r14
0x1801c8e2b  mov     rax, [rax+0F8h]
0x1801c8e32  call    cs:__guard_dispatch_icall_fptr
0x1801c8e38  mov     rsi, [rax]
0x1801c8e3b  mov     rcx, [rbp+var_10]
0x1801c8e3f  test    rcx, rcx
0x1801c8e42  jz      short loc_1801C8E51
0x1801c8e44  mov     rax, [rcx]
0x1801c8e47  mov     rax, [rax+8]
0x1801c8e4b  call    cs:__guard_dispatch_icall_fptr
0x1801c8e51  mov     rax, [rsi]
0x1801c8e54  mov     rcx, rsi
0x1801c8e57  mov     rax, [rax+18h]
0x1801c8e5b  call    cs:__guard_dispatch_icall_fptr
0x1801c8e61  test    al, al
0x1801c8e63  jnz     short loc_1801C8EAD
0x1801c8e65  mov     [rbp+arg_18], 0
0x1801c8e6d  lea     r8, [rbp+arg_18]
0x1801c8e71  mov     edx, r12d
0x1801c8e74  mov     rcx, rsi
0x1801c8e77  call    sub_180061960
0x1801c8e7c  test    al, al
0x1801c8e7e  jz      short loc_1801C8E9E
0x1801c8e80  xor     r8d, r8d
0x1801c8e83  mov     rdx, [rbp+arg_18]
0x1801c8e87  mov     rcx, [r15]
0x1801c8e8a  call    cs:__imp_GdipAddPathPath
0x1801c8e90  mov     r9d, 25454C7h
0x1801c8e96  mov     ecx, eax
0x1801c8e98  call    ?GdipStatus_ThrowOnFailureMessageTag@Gfx@@YAXW4Status@Gdiplus@@PEB_WW4Severity@Logging@Mso@@I@Z; Gfx::GdipStatus_ThrowOnFailureMessageTag(Gdiplus::Status,wchar_t const *,Mso::Logging::Severity,uint)
0x1801c8e9d  nop
0x1801c8e9e  mov     rcx, [rbp+arg_18]
0x1801c8ea2  test    rcx, rcx
0x1801c8ea5  jz      short loc_1801C8EAD
0x1801c8ea7  call    cs:__imp_GdipDeletePath
0x1801c8ead  inc     ebx
0x1801c8eaf  cmp     ebx, [rbp+arg_8]
0x1801c8eb2  jl      loc_1801C8E1E
0x1801c8eb8  mov     rax, rdi
0x1801c8ebb  add     rsp, 30h
0x1801c8ebf  pop     r15
0x1801c8ec1  pop     r14
0x1801c8ec3  pop     r12
0x1801c8ec5  pop     rdi
0x1801c8ec6  pop     rsi
0x1801c8ec7  pop     rbx
0x1801c8ec8  pop     rbp
0x1801c8ec9  retn
```
