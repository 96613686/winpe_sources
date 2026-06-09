# CGpuFrameDumper::CGpuFrameDumper(std::shared_ptr<CRdpIdMonitor> const &,Rdp::Avenc::IGpuFrameProcessor *)

- ea: `0x18002e41c`
- end: `0x18002e4da`
- name: `??0CGpuFrameDumper@@QEAA@AEBV?$shared_ptr@VCRdpIdMonitor@@@std@@PEAUIGpuFrameProcessor@Avenc@Rdp@@@Z`
- size: `190`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180023b6c`

## callees

- `0x18001ddf4`
- `0x18002de2c`
- `0x18002e41c`
- `0x18003f010`

## import_xrefs

- `d2d1!__imp_D2D1CreateFactory` at `0x18002e499`
- `d2d1!__imp_D2D1CreateFactory` at `0x18002e499`

## string_xrefs

- `0x18002e4aa`: `Failed to create D2D1 factory`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CGpuFrameDumper::CGpuFrameDumper(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rcx
  unsigned int v5; // eax
  const char *v7; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  D2D1_FACTORY_OPTIONS pFactoryOptions; // [rsp+58h] [rbp+20h] BYREF

  CFrameDumper<Rdp::Avenc::IGpuFrameProcessor>::CFrameDumper<Rdp::Avenc::IGpuFrameProcessor>(a1, a2, a3);
  *(_QWORD *)a1 = &CGpuFrameDumper::`vftable'{for `winrt::impl::producers_base<CFrameDumper<Rdp::Avenc::IGpuFrameProcessor>,std::tuple<Rdp::Avenc::IGpuFrameProcessor>>'};
  *(_QWORD *)(a1 + 8) = &CGpuFrameDumper::`vftable'{for `winrt::impl::root_implements<CFrameDumper<Rdp::Avenc::IGpuFrameProcessor>,Rdp::Avenc::IGpuFrameProcessor>'};
  *(_QWORD *)(a1 + 96) = 0;
  *(_QWORD *)(a1 + 104) = 0;
  *(_QWORD *)(a1 + 112) = 0;
  *(_QWORD *)(a1 + 120) = 0;
  *(_QWORD *)(a1 + 128) = 0;
  *(_QWORD *)(a1 + 136) = 0;
  pFactoryOptions.debugLevel = D2D1_DEBUG_LEVEL_NONE;
  v4 = *(_QWORD *)(a1 + 96);
  *(_QWORD *)(a1 + 96) = 0;
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  v5 = D2D1CreateFactory(
         D2D1_FACTORY_TYPE_SINGLE_THREADED,
         &GUID_bb12d362_daee_4b9a_aa1d_14ba401cfa1f,
         &pFactoryOptions,
         (void **)(a1 + 96));
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0xEC,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\framebuffer.cpp",
    (const char *)v5,
    (int)"Failed to create D2D1 factory",
    v7);
  return a1;
}

```

## disassembly

```asm
0x18002e41c  mov     [rsp+arg_8], rbx
0x18002e421  mov     [rsp+arg_0], rcx
0x18002e426  push    rdi
0x18002e427  sub     rsp, 30h
0x18002e42b  mov     rbx, rcx
0x18002e42e  call    ??0?$CFrameDumper@UIGpuFrameProcessor@Avenc@Rdp@@@@QEAA@AEBV?$shared_ptr@VCRdpIdMonitor@@@std@@PEAUIGpuFrameProcessor@Avenc@Rdp@@@Z; CFrameDumper<Rdp::Avenc::IGpuFrameProcessor>::CFrameDumper<Rdp::Avenc::IGpuFrameProcessor>(std::shared_ptr<CRdpIdMonitor> const &,Rdp::Avenc::IGpuFrameProcessor *)
0x18002e433  nop
0x18002e434  lea     rax, ??_7CGpuFrameDumper@@6B?$producers_base@V?$CFrameDumper@UIGpuFrameProcessor@Avenc@Rdp@@@@V?$tuple@UIGpuFrameProcessor@Avenc@Rdp@@@std@@@impl@winrt@@@; const CGpuFrameDumper::`vftable'{for `winrt::impl::producers_base<CFrameDumper<Rdp::Avenc::IGpuFrameProcessor>,std::tuple<Rdp::Avenc::IGpuFrameProcessor>>'}
0x18002e43b  mov     [rbx], rax
0x18002e43e  lea     rax, ??_7CGpuFrameDumper@@6B?$root_implements@V?$CFrameDumper@UIGpuFrameProcessor@Avenc@Rdp@@@@UIGpuFrameProcessor@Avenc@Rdp@@@impl@winrt@@@; const CGpuFrameDumper::`vftable'{for `winrt::impl::root_implements<CFrameDumper<Rdp::Avenc::IGpuFrameProcessor>,Rdp::Avenc::IGpuFrameProcessor>'}
0x18002e445  mov     [rbx+8], rax
0x18002e449  lea     rdi, [rbx+60h]
0x18002e44d  xor     eax, eax
0x18002e44f  mov     [rdi], rax
0x18002e452  mov     [rbx+68h], rax
0x18002e456  mov     [rbx+70h], rax
0x18002e45a  mov     [rbx+78h], rax
0x18002e45e  mov     [rbx+80h], rax
0x18002e465  mov     [rbx+88h], rax
0x18002e46c  mov     [rsp+38h+pFactoryOptions.debugLevel], eax
0x18002e470  mov     rcx, [rdi]
0x18002e473  mov     [rdi], rax
0x18002e476  test    rcx, rcx
0x18002e479  jz      short loc_18002E488
0x18002e47b  mov     rax, [rcx]
0x18002e47e  mov     rax, [rax+10h]
0x18002e482  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e487  nop
0x18002e488  mov     r9, rdi; ppIFactory
0x18002e48b  lea     r8, [rsp+38h+pFactoryOptions]; pFactoryOptions
0x18002e490  lea     rdx, _GUID_bb12d362_daee_4b9a_aa1d_14ba401cfa1f; riid
0x18002e497  xor     ecx, ecx; factoryType
0x18002e499  call    cs:__imp_D2D1CreateFactory
0x18002e4a0  nop     dword ptr [rax+rax+00h]
0x18002e4a5  mov     rcx, [rsp+38h]; this
0x18002e4aa  lea     rdx, aFailedToCreate_5; "Failed to create D2D1 factory"
0x18002e4b1  mov     qword ptr [rsp+38h+var_18], rdx; int
0x18002e4b6  mov     r9d, eax; char *
0x18002e4b9  lea     r8, aOnecoreuapTerm_17; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18002e4c0  mov     edx, 0ECh; void *
0x18002e4c5  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002e4ca  nop
0x18002e4cb  mov     rax, rbx
0x18002e4ce  mov     rbx, [rsp+38h+arg_8]
0x18002e4d3  add     rsp, 30h
0x18002e4d7  pop     rdi
0x18002e4d8  retn
```
