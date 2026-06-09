# Mso::SVG::SVGImage::AcquireEffectTree(Math::TAffine3x3<double> const &,GEL::IColorResolver const *)

- ea: `0x180005080`
- end: `0x1800052ac`
- name: `?AcquireEffectTree@SVGImage@SVG@Mso@@UEBA?AV?$TCntPtr@UITopLevelEffect@GEL@@@Ofc@@AEBU?$TAffine3x3@N@Math@@PEBUIColorResolver@GEL@@@Z`
- size: `556`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180005080`
- `0x1800f59e4`
- `0x1800f5ae4`
- `0x18013f810`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180005297`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800052a5`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180005297`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800052a5`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1800050bb`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1800050bb`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18000526a`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18000526a`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x1800050c6`
- `Mso20Win32Client!__imp_?ThrowOOM@@YAXXZ` at `0x1800050c6`
- `gfx!?Create@ITopLevelEffect@GEL@@SA?AV?$TCntPtr@UITopLevelEffect@GEL@@@Ofc@@W4RenderingPolicy@Gfx@@@Z` at `0x1800050ef`
- `gfx!?Create@ITopLevelEffect@GEL@@SA?AV?$TCntPtr@UITopLevelEffect@GEL@@@Ofc@@W4RenderingPolicy@Gfx@@@Z` at `0x1800050ef`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 **__fastcall Mso::SVG::SVGImage::AcquireEffectTree(__int64 a1, __int64 **a2, _OWORD *a3, __int64 a4)
{
  Mso::SVG::EnvironmentRenderer *v8; // rax
  __int64 v9; // rdi
  void *v10; // rdx
  __int64 *v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rax
  _BYTE *v14; // rsi
  char v15; // bl
  __int64 v16; // rax
  _BYTE *v17; // rbx
  __int64 v18; // rcx
  __int64 v20; // [rsp+40h] [rbp-11h] BYREF
  _QWORD v21[2]; // [rsp+48h] [rbp-9h] BYREF
  __m128i si128; // [rsp+58h] [rbp+7h] BYREF
  _OWORD v23[3]; // [rsp+68h] [rbp+17h] BYREF

  v8 = (Mso::SVG::EnvironmentRenderer *)Mso::Memory::AllocateEx((Mso::Memory *)0x50, 0, (unsigned int)a3);
  if ( !v8 )
  {
    ThrowOOM();
    __debugbreak();
  }
  v21[0] = v8;
  v9 = Mso::SVG::EnvironmentRenderer::EnvironmentRenderer(v8, *(struct Mso::SVG::Environment **)(a1 + 128));
  v21[1] = v9;
  GEL::ITopLevelEffect::Create(a2, 1);
  if ( v9 && !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a1 + 56LL))(a1) )
  {
    *(_OWORD *)(v9 + 16) = *a3;
    *(_OWORD *)(v9 + 32) = a3[1];
    *(_OWORD *)(v9 + 48) = a3[2];
    (*(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)a1 + 32LL))(a1, v21);
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    Mso::SVG::EnvironmentRenderer::RenderRoot(v9, (unsigned int)&v20, (unsigned int)v21, (unsigned int)&si128, a4);
    v11 = *a2;
    v12 = **a2;
    v23[0] = _mm_load_si128((const __m128i *)&_xmm);
    v23[1] = _mm_load_si128((const __m128i *)&_xmm);
    v23[2] = 0;
    (*(void (__fastcall **)(__int64 *, __int64, _OWORD *))(v12 + 120))(v11, v20, v23);
    v13 = *(_QWORD *)(v9 + 64);
    v14 = *(_BYTE **)(v13 + 528);
    if ( v14 )
    {
      (**(void (__fastcall ***)(_QWORD))v14)(*(_QWORD *)(v13 + 528));
      v15 = v14[536];
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v14 + 8LL))(v14);
      if ( !v15 )
        goto LABEL_9;
      *(_BYTE *)(a1 + 136) = 0;
      v16 = *(_QWORD *)(v9 + 64);
      v17 = *(_BYTE **)(v16 + 528);
      if ( v17 )
      {
        (**(void (__fastcall ***)(_QWORD))v17)(*(_QWORD *)(v16 + 528));
        v17[536] = 0;
        (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v17 + 8LL))(v17);
LABEL_9:
        if ( v20 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 8LL))(v20);
        goto LABEL_11;
      }
      CrashWithRecovery(0x1E3C3840u, 0);
    }
    CrashWithRecovery(0x1E3C3840u, 0);
    JUMPOUT(0x1800052ABLL);
  }
LABEL_11:
  if ( v9 )
  {
    v18 = *(_QWORD *)(v9 + 72);
    if ( v18 )
    {
      *(_QWORD *)(v9 + 72) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 8LL))(v18);
    }
    Mso::Memory::Free((Mso::Memory *)v9, v10);
  }
  return a2;
}

```

## disassembly

```asm
0x180005080  mov     rax, rsp
0x180005083  mov     [rax+8], rbx
0x180005087  mov     [rax+18h], rsi
0x18000508b  mov     [rax+20h], rdi
0x18000508f  mov     [rax+10h], rdx
0x180005093  push    rbp
0x180005094  push    r14
0x180005096  push    r15
0x180005098  lea     rbp, [rax-5Fh]
0x18000509c  sub     rsp, 90h
0x1800050a3  mov     rsi, r9
0x1800050a6  mov     rbx, r8
0x1800050a9  mov     r15, rdx
0x1800050ac  mov     r14, rcx
0x1800050af  mov     [rbp+57h+var_70], 0
0x1800050b6  xor     edx, edx
0x1800050b8  lea     ecx, [rdx+50h]
0x1800050bb  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x1800050c1  test    rax, rax
0x1800050c4  jnz     short loc_1800050CD
0x1800050c6  call    cs:__imp_?ThrowOOM@@YAXXZ; ThrowOOM(void)
0x1800050cc  int     3; Trap to Debugger
0x1800050cd  mov     [rbp+57h+var_60], rax
0x1800050d1  mov     rdx, [r14+80h]; struct Mso::SVG::Environment *
0x1800050d8  mov     rcx, rax; this
0x1800050db  call    ??0EnvironmentRenderer@SVG@Mso@@QEAA@AEAVEnvironment@12@@Z; Mso::SVG::EnvironmentRenderer::EnvironmentRenderer(Mso::SVG::Environment &)
0x1800050e0  mov     rdi, rax
0x1800050e3  mov     [rbp+57h+var_58], rax
0x1800050e7  mov     edx, 1
0x1800050ec  mov     rcx, r15
0x1800050ef  call    cs:__imp_?Create@ITopLevelEffect@GEL@@SA?AV?$TCntPtr@UITopLevelEffect@GEL@@@Ofc@@W4RenderingPolicy@Gfx@@@Z; GEL::ITopLevelEffect::Create(Gfx::RenderingPolicy)
0x1800050f5  mov     [rbp+57h+var_70], 1
0x1800050fc  test    rdi, rdi
0x1800050ff  jz      loc_180005244
0x180005105  mov     rcx, [r14]
0x180005108  mov     rax, [rcx+38h]
0x18000510c  mov     rcx, r14
0x18000510f  call    cs:__guard_dispatch_icall_fptr
0x180005115  test    al, al
0x180005117  jnz     loc_180005244
0x18000511d  movups  xmm0, xmmword ptr [rbx]
0x180005120  movups  xmmword ptr [rdi+10h], xmm0
0x180005124  movups  xmm1, xmmword ptr [rbx+10h]
0x180005128  movups  xmmword ptr [rdi+20h], xmm1
0x18000512c  movups  xmm0, xmmword ptr [rbx+20h]
0x180005130  movups  xmmword ptr [rdi+30h], xmm0
0x180005134  mov     rax, [r14]
0x180005137  lea     rdx, [rbp+57h+var_60]
0x18000513b  mov     rcx, r14
0x18000513e  mov     rax, [rax+20h]
0x180005142  call    cs:__guard_dispatch_icall_fptr
0x180005148  movdqa  xmm0, cs:__xmm@3ff00000000000003ff0000000000000
0x180005150  movups  [rbp+57h+var_50], xmm0
0x180005154  mov     [rsp+0A0h+var_80], rsi
0x180005159  lea     r9, [rbp+57h+var_50]
0x18000515d  lea     r8, [rbp+57h+var_60]
0x180005161  lea     rdx, [rbp+57h+var_68]
0x180005165  mov     rcx, rdi
0x180005168  call    ?RenderRoot@EnvironmentRenderer@SVG@Mso@@QEAA?AV?$TCntPtr@$$CBUIEffect@GEL@@@Ofc@@AEBU?$TSize@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@AEBU?$TScaling2@N@7@PEBUIColorResolver@GEL@@@Z; Mso::SVG::EnvironmentRenderer::RenderRoot(Math::TSize<Math::TUnits<uint,Math::DevicePixels>> const &,Math::TScaling2<double> const &,GEL::IColorResolver const *)
0x18000516d  nop
0x18000516e  mov     rcx, [r15]
0x180005171  mov     rax, [rcx]
0x180005174  movdqa  xmm0, cs:__xmm@000000000000000040c29a8000000000
0x18000517c  movups  [rbp+57h+var_40], xmm0
0x180005180  movdqa  xmm1, cs:__xmm@40c29a80000000000000000000000000
0x180005188  movups  [rbp+57h+var_30], xmm1
0x18000518c  xorps   xmm0, xmm0
0x18000518f  movups  [rbp+57h+var_20], xmm0
0x180005193  lea     r8, [rbp+57h+var_40]
0x180005197  mov     rdx, [rbp+57h+var_68]
0x18000519b  mov     rax, [rax+78h]
0x18000519f  call    cs:__guard_dispatch_icall_fptr
0x1800051a5  mov     rax, [rdi+40h]
0x1800051a9  mov     rsi, [rax+210h]
0x1800051b0  test    rsi, rsi
0x1800051b3  jz      short loc_1800051C5
0x1800051b5  mov     rax, [rsi]
0x1800051b8  mov     rcx, rsi
0x1800051bb  mov     rax, [rax]
0x1800051be  call    cs:__guard_dispatch_icall_fptr
0x1800051c4  nop
0x1800051c5  test    rsi, rsi
0x1800051c8  jz      loc_18000529E
0x1800051ce  mov     bl, [rsi+218h]
0x1800051d4  mov     rax, [rsi]
0x1800051d7  mov     rcx, rsi
0x1800051da  mov     rax, [rax+8]
0x1800051de  call    cs:__guard_dispatch_icall_fptr
0x1800051e4  test    bl, bl
0x1800051e6  jz      short loc_18000522D
0x1800051e8  mov     byte ptr [r14+88h], 0
0x1800051f0  mov     rax, [rdi+40h]
0x1800051f4  mov     rbx, [rax+210h]
0x1800051fb  test    rbx, rbx
0x1800051fe  jz      short loc_180005210
0x180005200  mov     rax, [rbx]
0x180005203  mov     rcx, rbx
0x180005206  mov     rax, [rax]
0x180005209  call    cs:__guard_dispatch_icall_fptr
0x18000520f  nop
0x180005210  test    rbx, rbx
0x180005213  jz      short loc_180005290
0x180005215  mov     byte ptr [rbx+218h], 0
0x18000521c  mov     rax, [rbx]
0x18000521f  mov     rcx, rbx
0x180005222  mov     rax, [rax+8]
0x180005226  call    cs:__guard_dispatch_icall_fptr
0x18000522c  nop
0x18000522d  mov     rcx, [rbp+57h+var_68]
0x180005231  test    rcx, rcx
0x180005234  jz      short loc_180005244
0x180005236  mov     rax, [rcx]
0x180005239  mov     rax, [rax+8]
0x18000523d  call    cs:__guard_dispatch_icall_fptr
0x180005243  nop
0x180005244  test    rdi, rdi
0x180005247  jz      short loc_180005270
0x180005249  mov     rcx, [rdi+48h]
0x18000524d  test    rcx, rcx
0x180005250  jz      short loc_180005267
0x180005252  mov     qword ptr [rdi+48h], 0
0x18000525a  mov     rax, [rcx]
0x18000525d  mov     rax, [rax+8]
0x180005261  call    cs:__guard_dispatch_icall_fptr
0x180005267  mov     rcx, rdi
0x18000526a  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x180005270  mov     rax, r15
0x180005273  lea     r11, [rsp+0A0h+var_10]
0x18000527b  mov     rbx, [r11+20h]
0x18000527f  mov     rsi, [r11+30h]
0x180005283  mov     rdi, [r11+38h]
0x180005287  mov     rsp, r11
0x18000528a  pop     r15
0x18000528c  pop     r14
0x18000528e  pop     rbp
0x18000528f  retn
0x180005290  xor     edx, edx
0x180005292  mov     ecx, 1E3C3840h
0x180005297  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18000529d  nop
0x18000529e  xor     edx, edx
0x1800052a0  mov     ecx, 1E3C3840h
0x1800052a5  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
