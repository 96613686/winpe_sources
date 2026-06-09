# MitigationOptionsPolicy::ImagePolicy::ImagePolicy(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180011858`
- end: `0x180011b88`
- name: `??0ImagePolicy@MitigationOptionsPolicy@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `816`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000a5f0`
- `0x1800127a8`

## callees

- `0x180002648`
- `0x180010634`
- `0x180010750`

## pseudocode

```c
__int64 __fastcall MitigationOptionsPolicy::ImagePolicy::ImagePolicy(__int64 a1, __int64 a2)
{
  std::wstring::wstring(a1, a2);
  MitigationOptionsPolicy::Policy::Policy(a1 + 32, a2, 0);
  *(_QWORD *)(a1 + 32) = &MitigationOptionsPolicy::AslrPolicy::`vftable';
  *(_OWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 96) = 0;
  *(_OWORD *)(a1 + 104) = 0;
  *(_QWORD *)(a1 + 120) = 0;
  MitigationOptionsPolicy::Policy::Policy(a1 + 128, a2, 0);
  *(_QWORD *)(a1 + 128) = &MitigationOptionsPolicy::DataExecutionPolicy::`vftable';
  *(_QWORD *)(a1 + 176) = 0;
  *(_QWORD *)(a1 + 184) = 0;
  MitigationOptionsPolicy::Policy::Policy(a1 + 192, a2, 0);
  *(_QWORD *)(a1 + 192) = &MitigationOptionsPolicy::HandlePolicy::`vftable';
  *(_QWORD *)(a1 + 240) = 0;
  *(_QWORD *)(a1 + 248) = 0;
  MitigationOptionsPolicy::Policy::Policy(a1 + 256, a2, 0);
  *(_QWORD *)(a1 + 256) = &MitigationOptionsPolicy::SysCallPolicy::`vftable';
  *(_OWORD *)(a1 + 304) = 0;
  *(_OWORD *)(a1 + 320) = 0;
  MitigationOptionsPolicy::Policy::Policy(a1 + 336, a2, 0);
  *(_QWORD *)(a1 + 336) = &MitigationOptionsPolicy::ExtensionPointPolicy::`vftable';
  *(_QWORD *)(a1 + 384) = 0;
  *(_QWORD *)(a1 + 392) = 0;
  MitigationOptionsPolicy::Policy::Policy(a1 + 400, a2, 0);
  *(_QWORD *)(a1 + 400) = &MitigationOptionsPolicy::DynamicCodePolicy::`vftable';
  *(_QWORD *)(a1 + 448) = 0;
  *(_QWORD *)(a1 + 456) = 0;
  MitigationOptionsPolicy::Policy::Policy(a1 + 464, a2, 0);
  *(_QWORD *)(a1 + 464) = &MitigationOptionsPolicy::ControlFlowGuardPolicy::`vftable';
  *(_OWORD *)(a1 + 512) = 0;
  *(_OWORD *)(a1 + 528) = 0;
  MitigationOptionsPolicy::Policy::Policy(a1 + 544, a2, 0);
  *(_QWORD *)(a1 + 544) = &MitigationOptionsPolicy::BinarySigningPolicy::`vftable';
  *(_OWORD *)(a1 + 592) = 0;
  *(_OWORD *)(a1 + 608) = 0;
  MitigationOptionsPolicy::Policy::Policy(a1 + 624, a2, 0);
  *(_QWORD *)(a1 + 624) = &MitigationOptionsPolicy::FontPolicy::`vftable';
  *(_QWORD *)(a1 + 672) = 0;
  *(_QWORD *)(a1 + 680) = 0;
  MitigationOptionsPolicy::Policy::Policy(a1 + 688, a2, 0);
  *(_QWORD *)(a1 + 688) = &MitigationOptionsPolicy::ImageLoadPolicy::`vftable';
  *(_OWORD *)(a1 + 736) = 0;
  *(_QWORD *)(a1 + 752) = 0;
  *(_OWORD *)(a1 + 760) = 0;
  *(_QWORD *)(a1 + 776) = 0;
  MitigationOptionsPolicy::Policy::Policy(a1 + 784, a2, 0);
  *(_QWORD *)(a1 + 784) = &MitigationOptionsPolicy::PayloadRestrictionPolicy::`vftable';
  memset_0((void *)(a1 + 832), 0, 0x430u);
  memset_0((void *)(a1 + 1904), 0, 0x430u);
  MitigationOptionsPolicy::Policy::Policy(a1 + 2976, a2, 0);
  *(_QWORD *)(a1 + 2976) = &MitigationOptionsPolicy::SehopPolicy::`vftable';
  *(_QWORD *)(a1 + 3024) = 0;
  *(_QWORD *)(a1 + 3032) = 0;
  MitigationOptionsPolicy::Policy::Policy(a1 + 3040, a2, 0);
  *(_QWORD *)(a1 + 3040) = &MitigationOptionsPolicy::HeapPolicy::`vftable';
  *(_QWORD *)(a1 + 3088) = 0;
  *(_QWORD *)(a1 + 3096) = 0;
  MitigationOptionsPolicy::Policy::Policy(a1 + 3104, a2, 0);
  *(_QWORD *)(a1 + 3104) = &MitigationOptionsPolicy::ChildProcessPolicy::`vftable';
  *(_QWORD *)(a1 + 3152) = 0;
  *(_QWORD *)(a1 + 3160) = 0;
  MitigationOptionsPolicy::Policy::Policy(a1 + 3168, a2, 0);
  *(_QWORD *)(a1 + 3168) = &MitigationOptionsPolicy::UserShadowStackPolicy::`vftable';
  *(_OWORD *)(a1 + 3216) = 0;
  *(_QWORD *)(a1 + 3232) = 0;
  *(_OWORD *)(a1 + 3240) = 0;
  *(_QWORD *)(a1 + 3256) = 0;
  MitigationOptionsPolicy::Policy::Policy(a1 + 3264, a2, 0);
  *(_QWORD *)(a1 + 3264) = &MitigationOptionsPolicy::UserPointerAuthPolicy::`vftable';
  *(_QWORD *)(a1 + 3312) = 0;
  *(_QWORD *)(a1 + 3320) = 0;
  MitigationOptionsPolicy::Policy::Policy(a1 + 3328, a2, 0);
  *(_QWORD *)(a1 + 3328) = &MitigationOptionsPolicy::RedirectionTrustPolicy::`vftable';
  *(_QWORD *)(a1 + 3376) = 0;
  *(_QWORD *)(a1 + 3384) = 0;
  return a1;
}

```

## disassembly

```asm
0x180011858  mov     [rsp+arg_8], rbx
0x18001185d  mov     [rsp+arg_10], rsi
0x180011862  mov     [rsp+arg_0], rcx
0x180011867  push    rdi
0x180011868  sub     rsp, 20h
0x18001186c  mov     rdi, rdx
0x18001186f  mov     rsi, rcx
0x180011872  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180011877  nop
0x180011878  xor     r8d, r8d
0x18001187b  mov     rdx, rdi
0x18001187e  lea     rcx, [rsi+20h]
0x180011882  call    ??0Policy@MitigationOptionsPolicy@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; MitigationOptionsPolicy::Policy::Policy(std::wstring const &,bool)
0x180011887  lea     rax, ??_7AslrPolicy@MitigationOptionsPolicy@@6B@; const MitigationOptionsPolicy::AslrPolicy::`vftable'
0x18001188e  mov     [rsi+20h], rax
0x180011892  xorps   xmm0, xmm0
0x180011895  xor     eax, eax
0x180011897  movups  xmmword ptr [rsi+50h], xmm0
0x18001189b  mov     [rsi+60h], rax
0x18001189f  movups  xmmword ptr [rsi+68h], xmm0
0x1800118a3  mov     [rsi+78h], rax
0x1800118a7  lea     rbx, [rsi+80h]
0x1800118ae  xor     r8d, r8d
0x1800118b1  mov     rdx, rdi
0x1800118b4  mov     rcx, rbx
0x1800118b7  call    ??0Policy@MitigationOptionsPolicy@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; MitigationOptionsPolicy::Policy::Policy(std::wstring const &,bool)
0x1800118bc  lea     rax, ??_7DataExecutionPolicy@MitigationOptionsPolicy@@6B@; const MitigationOptionsPolicy::DataExecutionPolicy::`vftable'
0x1800118c3  mov     [rbx], rax
0x1800118c6  xor     eax, eax
0x1800118c8  mov     [rbx+30h], rax
0x1800118cc  mov     [rbx+38h], rax
0x1800118d0  lea     rbx, [rsi+0C0h]
0x1800118d7  xor     r8d, r8d
0x1800118da  mov     rdx, rdi
0x1800118dd  mov     rcx, rbx
0x1800118e0  call    ??0Policy@MitigationOptionsPolicy@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; MitigationOptionsPolicy::Policy::Policy(std::wstring const &,bool)
0x1800118e5  lea     rax, ??_7HandlePolicy@MitigationOptionsPolicy@@6B@; const MitigationOptionsPolicy::HandlePolicy::`vftable'
0x1800118ec  mov     [rbx], rax
0x1800118ef  xor     eax, eax
0x1800118f1  mov     [rbx+30h], rax
0x1800118f5  mov     [rbx+38h], rax
0x1800118f9  lea     rbx, [rsi+100h]
0x180011900  xor     r8d, r8d
0x180011903  mov     rdx, rdi
0x180011906  mov     rcx, rbx
0x180011909  call    ??0Policy@MitigationOptionsPolicy@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; MitigationOptionsPolicy::Policy::Policy(std::wstring const &,bool)
0x18001190e  lea     rax, ??_7SysCallPolicy@MitigationOptionsPolicy@@6B@; const MitigationOptionsPolicy::SysCallPolicy::`vftable'
0x180011915  mov     [rbx], rax
0x180011918  xorps   xmm0, xmm0
0x18001191b  movups  xmmword ptr [rbx+30h], xmm0
0x18001191f  xorps   xmm1, xmm1
0x180011922  movups  xmmword ptr [rbx+40h], xmm1
0x180011926  lea     rbx, [rsi+150h]
0x18001192d  xor     r8d, r8d
0x180011930  mov     rdx, rdi
0x180011933  mov     rcx, rbx
0x180011936  call    ??0Policy@MitigationOptionsPolicy@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; MitigationOptionsPolicy::Policy::Policy(std::wstring const &,bool)
0x18001193b  lea     rax, ??_7ExtensionPointPolicy@MitigationOptionsPolicy@@6B@; const MitigationOptionsPolicy::ExtensionPointPolicy::`vftable'
0x180011942  mov     [rbx], rax
0x180011945  xor     eax, eax
0x180011947  mov     [rbx+30h], rax
0x18001194b  mov     [rbx+38h], rax
0x18001194f  lea     rbx, [rsi+190h]
0x180011956  xor     r8d, r8d
0x180011959  mov     rdx, rdi
0x18001195c  mov     rcx, rbx
0x18001195f  call    ??0Policy@MitigationOptionsPolicy@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; MitigationOptionsPolicy::Policy::Policy(std::wstring const &,bool)
0x180011964  lea     rax, ??_7DynamicCodePolicy@MitigationOptionsPolicy@@6B@; const MitigationOptionsPolicy::DynamicCodePolicy::`vftable'
0x18001196b  mov     [rbx], rax
0x18001196e  xor     eax, eax
0x180011970  mov     [rbx+30h], rax
0x180011974  mov     [rbx+38h], rax
0x180011978  lea     rbx, [rsi+1D0h]
0x18001197f  xor     r8d, r8d
0x180011982  mov     rdx, rdi
0x180011985  mov     rcx, rbx
0x180011988  call    ??0Policy@MitigationOptionsPolicy@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; MitigationOptionsPolicy::Policy::Policy(std::wstring const &,bool)
0x18001198d  lea     rax, ??_7ControlFlowGuardPolicy@MitigationOptionsPolicy@@6B@; const MitigationOptionsPolicy::ControlFlowGuardPolicy::`vftable'
0x180011994  mov     [rbx], rax
0x180011997  xorps   xmm0, xmm0
0x18001199a  movups  xmmword ptr [rbx+30h], xmm0
0x18001199e  xorps   xmm1, xmm1
0x1800119a1  movups  xmmword ptr [rbx+40h], xmm1
0x1800119a5  lea     rbx, [rsi+220h]
0x1800119ac  xor     r8d, r8d
0x1800119af  mov     rdx, rdi
0x1800119b2  mov     rcx, rbx
0x1800119b5  call    ??0Policy@MitigationOptionsPolicy@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; MitigationOptionsPolicy::Policy::Policy(std::wstring const &,bool)
0x1800119ba  lea     rax, ??_7BinarySigningPolicy@MitigationOptionsPolicy@@6B@; const MitigationOptionsPolicy::BinarySigningPolicy::`vftable'
0x1800119c1  mov     [rbx], rax
0x1800119c4  xorps   xmm0, xmm0
0x1800119c7  movups  xmmword ptr [rbx+30h], xmm0
0x1800119cb  xorps   xmm1, xmm1
0x1800119ce  movups  xmmword ptr [rbx+40h], xmm1
0x1800119d2  lea     rbx, [rsi+270h]
0x1800119d9  xor     r8d, r8d
0x1800119dc  mov     rdx, rdi
0x1800119df  mov     rcx, rbx
0x1800119e2  call    ??0Policy@MitigationOptionsPolicy@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; MitigationOptionsPolicy::Policy::Policy(std::wstring const &,bool)
0x1800119e7  lea     rax, ??_7FontPolicy@MitigationOptionsPolicy@@6B@; const MitigationOptionsPolicy::FontPolicy::`vftable'
0x1800119ee  mov     [rbx], rax
0x1800119f1  xor     eax, eax
0x1800119f3  mov     [rbx+30h], rax
0x1800119f7  mov     [rbx+38h], rax
0x1800119fb  lea     rbx, [rsi+2B0h]
0x180011a02  xor     r8d, r8d
0x180011a05  mov     rdx, rdi
0x180011a08  mov     rcx, rbx
0x180011a0b  call    ??0Policy@MitigationOptionsPolicy@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; MitigationOptionsPolicy::Policy::Policy(std::wstring const &,bool)
0x180011a10  lea     rax, ??_7ImageLoadPolicy@MitigationOptionsPolicy@@6B@; const MitigationOptionsPolicy::ImageLoadPolicy::`vftable'
0x180011a17  mov     [rbx], rax
0x180011a1a  xorps   xmm0, xmm0
0x180011a1d  xor     eax, eax
0x180011a1f  movups  xmmword ptr [rbx+30h], xmm0
0x180011a23  mov     [rbx+40h], rax
0x180011a27  movups  xmmword ptr [rbx+48h], xmm0
0x180011a2b  mov     [rbx+58h], rax
0x180011a2f  lea     rbx, [rsi+310h]
0x180011a36  xor     r8d, r8d
0x180011a39  mov     rdx, rdi
0x180011a3c  mov     rcx, rbx
0x180011a3f  call    ??0Policy@MitigationOptionsPolicy@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; MitigationOptionsPolicy::Policy::Policy(std::wstring const &,bool)
0x180011a44  lea     rax, ??_7PayloadRestrictionPolicy@MitigationOptionsPolicy@@6B@; const MitigationOptionsPolicy::PayloadRestrictionPolicy::`vftable'
0x180011a4b  mov     [rbx], rax
0x180011a4e  lea     rcx, [rbx+30h]; void *
0x180011a52  xor     edx, edx; Val
0x180011a54  mov     r8d, 430h; Size
0x180011a5a  call    memset_0
0x180011a5f  lea     rcx, [rbx+460h]; void *
0x180011a66  xor     edx, edx; Val
0x180011a68  mov     r8d, 430h; Size
0x180011a6e  call    memset_0
0x180011a73  nop
0x180011a74  lea     rbx, [rsi+0BA0h]
0x180011a7b  xor     r8d, r8d
0x180011a7e  mov     rdx, rdi
0x180011a81  mov     rcx, rbx
0x180011a84  call    ??0Policy@MitigationOptionsPolicy@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; MitigationOptionsPolicy::Policy::Policy(std::wstring const &,bool)
0x180011a89  lea     rax, ??_7SehopPolicy@MitigationOptionsPolicy@@6B@; const MitigationOptionsPolicy::SehopPolicy::`vftable'
0x180011a90  mov     [rbx], rax
0x180011a93  xor     eax, eax
0x180011a95  mov     [rbx+30h], rax
0x180011a99  mov     [rbx+38h], rax
0x180011a9d  lea     rbx, [rsi+0BE0h]
0x180011aa4  xor     r8d, r8d
0x180011aa7  mov     rdx, rdi
0x180011aaa  mov     rcx, rbx
0x180011aad  call    ??0Policy@MitigationOptionsPolicy@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; MitigationOptionsPolicy::Policy::Policy(std::wstring const &,bool)
0x180011ab2  lea     rax, ??_7HeapPolicy@MitigationOptionsPolicy@@6B@; const MitigationOptionsPolicy::HeapPolicy::`vftable'
0x180011ab9  mov     [rbx], rax
0x180011abc  xor     eax, eax
0x180011abe  mov     [rbx+30h], rax
0x180011ac2  mov     [rbx+38h], rax
0x180011ac6  lea     rbx, [rsi+0C20h]
0x180011acd  xor     r8d, r8d
0x180011ad0  mov     rdx, rdi
0x180011ad3  mov     rcx, rbx
0x180011ad6  call    ??0Policy@MitigationOptionsPolicy@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; MitigationOptionsPolicy::Policy::Policy(std::wstring const &,bool)
0x180011adb  lea     rax, ??_7ChildProcessPolicy@MitigationOptionsPolicy@@6B@; const MitigationOptionsPolicy::ChildProcessPolicy::`vftable'
0x180011ae2  mov     [rbx], rax
0x180011ae5  xor     eax, eax
0x180011ae7  mov     [rbx+30h], rax
0x180011aeb  mov     [rbx+38h], rax
0x180011aef  lea     rbx, [rsi+0C60h]
0x180011af6  xor     r8d, r8d
0x180011af9  mov     rdx, rdi
0x180011afc  mov     rcx, rbx
0x180011aff  call    ??0Policy@MitigationOptionsPolicy@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; MitigationOptionsPolicy::Policy::Policy(std::wstring const &,bool)
0x180011b04  lea     rax, ??_7UserShadowStackPolicy@MitigationOptionsPolicy@@6B@; const MitigationOptionsPolicy::UserShadowStackPolicy::`vftable'
0x180011b0b  mov     [rbx], rax
0x180011b0e  xorps   xmm0, xmm0
0x180011b11  xor     eax, eax
0x180011b13  movups  xmmword ptr [rbx+30h], xmm0
0x180011b17  mov     [rbx+40h], rax
0x180011b1b  movups  xmmword ptr [rbx+48h], xmm0
0x180011b1f  mov     [rbx+58h], rax
0x180011b23  lea     rbx, [rsi+0CC0h]
0x180011b2a  xor     r8d, r8d
0x180011b2d  mov     rdx, rdi
0x180011b30  mov     rcx, rbx
0x180011b33  call    ??0Policy@MitigationOptionsPolicy@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; MitigationOptionsPolicy::Policy::Policy(std::wstring const &,bool)
0x180011b38  lea     rax, ??_7UserPointerAuthPolicy@MitigationOptionsPolicy@@6B@; const MitigationOptionsPolicy::UserPointerAuthPolicy::`vftable'
0x180011b3f  mov     [rbx], rax
0x180011b42  xor     eax, eax
0x180011b44  mov     [rbx+30h], rax
0x180011b48  mov     [rbx+38h], rax
0x180011b4c  lea     rbx, [rsi+0D00h]
0x180011b53  xor     r8d, r8d
0x180011b56  mov     rdx, rdi
0x180011b59  mov     rcx, rbx
0x180011b5c  call    ??0Policy@MitigationOptionsPolicy@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; MitigationOptionsPolicy::Policy::Policy(std::wstring const &,bool)
0x180011b61  lea     rax, ??_7RedirectionTrustPolicy@MitigationOptionsPolicy@@6B@; const MitigationOptionsPolicy::RedirectionTrustPolicy::`vftable'
0x180011b68  mov     [rbx], rax
0x180011b6b  xor     eax, eax
0x180011b6d  mov     [rbx+30h], rax
0x180011b71  mov     [rbx+38h], rax
0x180011b75  mov     rax, rsi
0x180011b78  mov     rbx, [rsp+28h+arg_8]
0x180011b7d  mov     rsi, [rsp+28h+arg_10]
0x180011b82  add     rsp, 20h
0x180011b86  pop     rdi
0x180011b87  retn
```
