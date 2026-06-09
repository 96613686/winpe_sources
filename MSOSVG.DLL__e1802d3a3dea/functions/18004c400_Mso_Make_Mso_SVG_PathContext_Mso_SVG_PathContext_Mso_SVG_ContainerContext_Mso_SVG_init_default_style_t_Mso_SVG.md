# Mso::Make<Mso::SVG::PathContext,Mso::SVG::PathContext,Mso::SVG::ContainerContext &,Mso::SVG::init_default_style_t>(Mso::SVG::ContainerContext &,Mso::SVG::init_default_style_t &&)

- ea: `0x18004c400`
- end: `0x18004c4f1`
- name: `??$Make@VPathContext@SVG@Mso@@V123@AEAVContainerContext@23@Uinit_default_style_t@23@@Mso@@YA?AV?$TCntPtr@VPathContext@SVG@Mso@@@0@AEAVContainerContext@SVG@0@$$QEAUinit_default_style_t@30@@Z`
- size: `241`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180048724`

## callees

- `0x180045c6c`
- `0x18004c400`
- `0x18013f760`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x18004c4ea`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x18004c4ea`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x18004c42b`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x18004c42b`
- `gfx!??0PathBuilder@GEL@@QEAA@XZ` at `0x18004c469`
- `gfx!??0PathBuilder@GEL@@QEAA@XZ` at `0x18004c469`
- `gfx!?Create@IEmptyPath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@XZ` at `0x18004c475`
- `gfx!?Create@IEmptyPath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@XZ` at `0x18004c475`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall Mso::Make<Mso::SVG::PathContext,Mso::SVG::PathContext,Mso::SVG::ContainerContext &,Mso::SVG::init_default_style_t>(
        _QWORD *a1,
        __int64 a2,
        _BYTE *a3)
{
  _QWORD *v6; // rax
  __int64 v7; // r8
  __int64 v8; // r9
  _QWORD *v9; // rbx
  void (__fastcall ****v10)(_QWORD); // rax
  void (__fastcall ***v11)(_QWORD); // rcx
  __int64 v13; // [rsp+68h] [rbp+20h] BYREF

  v6 = Mso::Memory::AllocateEx((Mso::Memory *)0x208, 0, (unsigned int)a3);
  v9 = v6;
  if ( !v6 )
  {
    CrashWithRecoveryOnOOM(0x1F65259Du);
    JUMPOUT(0x18004C4F0LL);
  }
  LOBYTE(v8) = 1;
  LOBYTE(v7) = *a3;
  Mso::SVG::ShapeContext::ShapeContext(v6, a2, v7, v8);
  *v9 = &Mso::SVG::PathContext::`vftable';
  GEL::PathBuilder::PathBuilder((GEL::PathBuilder *)(v9 + 51));
  v10 = (void (__fastcall ****)(_QWORD))GEL::IEmptyPath::Create(&v13);
  v11 = *v10;
  v9[59] = *v10;
  if ( v11 )
    (**v11)(v11);
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13);
  v9[60] = 0;
  v9[61] = 0;
  *((_BYTE *)v9 + 512) = 0;
  *a1 = v9;
  return a1;
}

```

## disassembly

```asm
0x18004c400  mov     rax, rsp
0x18004c403  mov     [rax+8], rbx
0x18004c407  mov     [rax+10h], rbp
0x18004c40b  mov     [rax+18h], rsi
0x18004c40f  push    rdi
0x18004c410  sub     rsp, 40h
0x18004c414  mov     rsi, r8
0x18004c417  mov     rbp, rdx
0x18004c41a  mov     rdi, rcx
0x18004c41d  xorps   xmm0, xmm0
0x18004c420  movups  xmmword ptr [rax-18h], xmm0
0x18004c424  xor     edx, edx
0x18004c426  mov     ecx, 208h
0x18004c42b  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x18004c431  mov     rbx, rax
0x18004c434  mov     [rsp+48h+var_18], rax
0x18004c439  test    rax, rax
0x18004c43c  jz      loc_18004C4E5
0x18004c442  mov     [rsp+48h+var_20], rax
0x18004c447  mov     r9b, 1
0x18004c44a  mov     r8b, [rsi]
0x18004c44d  mov     rdx, rbp
0x18004c450  mov     rcx, rax
0x18004c453  call    ??0ShapeContext@SVG@Mso@@QEAA@AEAVStylableContext@12@Uinit_default_style_t@12@_N@Z; Mso::SVG::ShapeContext::ShapeContext(Mso::SVG::StylableContext &,Mso::SVG::init_default_style_t,bool)
0x18004c458  lea     rax, ??_7PathContext@SVG@Mso@@6B@; const Mso::SVG::PathContext::`vftable'
0x18004c45f  mov     [rbx], rax
0x18004c462  lea     rcx, [rbx+198h]
0x18004c469  call    cs:__imp_??0PathBuilder@GEL@@QEAA@XZ; GEL::PathBuilder::PathBuilder(void)
0x18004c46f  nop
0x18004c470  lea     rcx, [rsp+48h+arg_18]
0x18004c475  call    cs:__imp_?Create@IEmptyPath@GEL@@SA?AV?$TCntPtr@UIPath@GEL@@@Ofc@@XZ; GEL::IEmptyPath::Create(void)
0x18004c47b  mov     rcx, [rax]
0x18004c47e  mov     [rbx+1D8h], rcx
0x18004c485  test    rcx, rcx
0x18004c488  jz      short loc_18004C496
0x18004c48a  mov     rax, [rcx]
0x18004c48d  mov     rax, [rax]
0x18004c490  call    cs:__guard_dispatch_icall_fptr
0x18004c496  mov     rcx, [rsp+48h+arg_18]
0x18004c49b  test    rcx, rcx
0x18004c49e  jz      short loc_18004C4AD
0x18004c4a0  mov     rax, [rcx]
0x18004c4a3  mov     rax, [rax+8]
0x18004c4a7  call    cs:__guard_dispatch_icall_fptr
0x18004c4ad  mov     qword ptr [rbx+1E0h], 0
0x18004c4b8  mov     qword ptr [rbx+1E8h], 0
0x18004c4c3  mov     byte ptr [rbx+200h], 0
0x18004c4ca  mov     [rdi], rbx
0x18004c4cd  mov     rax, rdi
0x18004c4d0  mov     rbx, [rsp+48h+arg_0]
0x18004c4d5  mov     rbp, [rsp+48h+arg_8]
0x18004c4da  mov     rsi, [rsp+48h+arg_10]
0x18004c4df  add     rsp, 40h
0x18004c4e3  pop     rdi
0x18004c4e4  retn
0x18004c4e5  mov     ecx, 1F65259Dh
0x18004c4ea  call    cs:__imp_?CrashWithRecoveryOnOOM@@YAXI@Z; CrashWithRecoveryOnOOM(uint)
```
