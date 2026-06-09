# MitigationOptionsPolicy::ImagePolicy::ImagePolicy(bool)

- ea: `0x180011b90`
- end: `0x180012086`
- name: `??0ImagePolicy@MitigationOptionsPolicy@@QEAA@_N@Z`
- size: `1270`
- prototype: `MitigationOptionsPolicy::ImagePolicy *__fastcall(MitigationOptionsPolicy::ImagePolicy *this, char)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180009f70`
- `0x18000a5f0`

## callees

- `0x180001c00`
- `0x180002648`
- `0x1800074d8`
- `0x1800076b4`
- `0x180010750`

## pseudocode

```c
MitigationOptionsPolicy::ImagePolicy *__fastcall MitigationOptionsPolicy::ImagePolicy::ImagePolicy(
        MitigationOptionsPolicy::ImagePolicy *this,
        char a2)
{
  __int64 v4; // r8
  __int64 v5; // r8
  __int64 v6; // r8
  __int64 v7; // r8
  __int64 v8; // r8
  __int64 v9; // r8
  __int64 v10; // r8
  __int64 v11; // r8
  __int64 v12; // r8
  __int64 v13; // r8
  __int64 v14; // r8
  __int64 v15; // r8
  __int64 v16; // r8
  __int64 v17; // r8
  __int64 v18; // r8
  __int64 v19; // r8
  __int64 v20; // r8
  _QWORD v22[4]; // [rsp+28h] [rbp-28h] BYREF

  std::wstring::wstring(this, &qword_180018390);
  std::wstring::wstring(v22, &qword_180018390);
  LOBYTE(v4) = a2;
  MitigationOptionsPolicy::Policy::Policy((char *)this + 32, v22, v4);
  std::wstring::~wstring(v22);
  *((_QWORD *)this + 4) = &MitigationOptionsPolicy::AslrPolicy::`vftable';
  *((_OWORD *)this + 5) = 0;
  *((_QWORD *)this + 12) = 0;
  *(_OWORD *)((char *)this + 104) = 0;
  *((_QWORD *)this + 15) = 0;
  std::wstring::wstring(v22, &qword_180018390);
  LOBYTE(v5) = a2;
  MitigationOptionsPolicy::Policy::Policy((char *)this + 128, v22, v5);
  std::wstring::~wstring(v22);
  *((_QWORD *)this + 16) = &MitigationOptionsPolicy::DataExecutionPolicy::`vftable';
  *((_QWORD *)this + 22) = 0;
  *((_QWORD *)this + 23) = 0;
  std::wstring::wstring(v22, &qword_180018390);
  LOBYTE(v6) = a2;
  MitigationOptionsPolicy::Policy::Policy((char *)this + 192, v22, v6);
  std::wstring::~wstring(v22);
  *((_QWORD *)this + 24) = &MitigationOptionsPolicy::HandlePolicy::`vftable';
  *((_QWORD *)this + 30) = 0;
  *((_QWORD *)this + 31) = 0;
  std::wstring::wstring(v22, &qword_180018390);
  LOBYTE(v7) = a2;
  MitigationOptionsPolicy::Policy::Policy((char *)this + 256, v22, v7);
  std::wstring::~wstring(v22);
  *((_QWORD *)this + 32) = &MitigationOptionsPolicy::SysCallPolicy::`vftable';
  *((_OWORD *)this + 19) = 0;
  *((_OWORD *)this + 20) = 0;
  std::wstring::wstring(v22, &qword_180018390);
  LOBYTE(v8) = a2;
  MitigationOptionsPolicy::Policy::Policy((char *)this + 336, v22, v8);
  std::wstring::~wstring(v22);
  *((_QWORD *)this + 42) = &MitigationOptionsPolicy::ExtensionPointPolicy::`vftable';
  *((_QWORD *)this + 48) = 0;
  *((_QWORD *)this + 49) = 0;
  std::wstring::wstring(v22, &qword_180018390);
  LOBYTE(v9) = a2;
  MitigationOptionsPolicy::Policy::Policy((char *)this + 400, v22, v9);
  std::wstring::~wstring(v22);
  *((_QWORD *)this + 50) = &MitigationOptionsPolicy::DynamicCodePolicy::`vftable';
  *((_QWORD *)this + 56) = 0;
  *((_QWORD *)this + 57) = 0;
  std::wstring::wstring(v22, &qword_180018390);
  LOBYTE(v10) = a2;
  MitigationOptionsPolicy::Policy::Policy((char *)this + 464, v22, v10);
  std::wstring::~wstring(v22);
  *((_QWORD *)this + 58) = &MitigationOptionsPolicy::ControlFlowGuardPolicy::`vftable';
  *((_OWORD *)this + 32) = 0;
  *((_OWORD *)this + 33) = 0;
  std::wstring::wstring(v22, &qword_180018390);
  LOBYTE(v11) = a2;
  MitigationOptionsPolicy::Policy::Policy((char *)this + 544, v22, v11);
  std::wstring::~wstring(v22);
  *((_QWORD *)this + 68) = &MitigationOptionsPolicy::BinarySigningPolicy::`vftable';
  *((_OWORD *)this + 37) = 0;
  *((_OWORD *)this + 38) = 0;
  std::wstring::wstring(v22, &qword_180018390);
  LOBYTE(v12) = a2;
  MitigationOptionsPolicy::Policy::Policy((char *)this + 624, v22, v12);
  std::wstring::~wstring(v22);
  *((_QWORD *)this + 78) = &MitigationOptionsPolicy::FontPolicy::`vftable';
  *((_QWORD *)this + 84) = 0;
  *((_QWORD *)this + 85) = 0;
  std::wstring::wstring(v22, &qword_180018390);
  LOBYTE(v13) = a2;
  MitigationOptionsPolicy::Policy::Policy((char *)this + 688, v22, v13);
  std::wstring::~wstring(v22);
  *((_QWORD *)this + 86) = &MitigationOptionsPolicy::ImageLoadPolicy::`vftable';
  *((_OWORD *)this + 46) = 0;
  *((_QWORD *)this + 94) = 0;
  *(_OWORD *)((char *)this + 760) = 0;
  *((_QWORD *)this + 97) = 0;
  std::wstring::wstring(v22, &qword_180018390);
  LOBYTE(v14) = a2;
  MitigationOptionsPolicy::Policy::Policy((char *)this + 784, v22, v14);
  std::wstring::~wstring(v22);
  *((_QWORD *)this + 98) = &MitigationOptionsPolicy::PayloadRestrictionPolicy::`vftable';
  memset_0((char *)this + 832, 0, 0x430u);
  memset_0((char *)this + 1904, 0, 0x430u);
  std::wstring::wstring(v22, &qword_180018390);
  LOBYTE(v15) = a2;
  MitigationOptionsPolicy::Policy::Policy((char *)this + 2976, v22, v15);
  std::wstring::~wstring(v22);
  *((_QWORD *)this + 372) = &MitigationOptionsPolicy::SehopPolicy::`vftable';
  *((_QWORD *)this + 378) = 0;
  *((_QWORD *)this + 379) = 0;
  std::wstring::wstring(v22, &qword_180018390);
  LOBYTE(v16) = a2;
  MitigationOptionsPolicy::Policy::Policy((char *)this + 3040, v22, v16);
  std::wstring::~wstring(v22);
  *((_QWORD *)this + 380) = &MitigationOptionsPolicy::HeapPolicy::`vftable';
  *((_QWORD *)this + 386) = 0;
  *((_QWORD *)this + 387) = 0;
  std::wstring::wstring(v22, &qword_180018390);
  LOBYTE(v17) = a2;
  MitigationOptionsPolicy::Policy::Policy((char *)this + 3104, v22, v17);
  std::wstring::~wstring(v22);
  *((_QWORD *)this + 388) = &MitigationOptionsPolicy::ChildProcessPolicy::`vftable';
  *((_QWORD *)this + 394) = 0;
  *((_QWORD *)this + 395) = 0;
  std::wstring::wstring(v22, &qword_180018390);
  LOBYTE(v18) = a2;
  MitigationOptionsPolicy::Policy::Policy((char *)this + 3168, v22, v18);
  std::wstring::~wstring(v22);
  *((_QWORD *)this + 396) = &MitigationOptionsPolicy::UserShadowStackPolicy::`vftable';
  *((_OWORD *)this + 201) = 0;
  *((_QWORD *)this + 404) = 0;
  *(_OWORD *)((char *)this + 3240) = 0;
  *((_QWORD *)this + 407) = 0;
  std::wstring::wstring(v22, &qword_180018390);
  LOBYTE(v19) = a2;
  MitigationOptionsPolicy::Policy::Policy((char *)this + 3264, v22, v19);
  std::wstring::~wstring(v22);
  *((_QWORD *)this + 408) = &MitigationOptionsPolicy::UserPointerAuthPolicy::`vftable';
  *((_QWORD *)this + 414) = 0;
  *((_QWORD *)this + 415) = 0;
  std::wstring::wstring(v22, &qword_180018390);
  LOBYTE(v20) = a2;
  MitigationOptionsPolicy::Policy::Policy((char *)this + 3328, v22, v20);
  std::wstring::~wstring(v22);
  *((_QWORD *)this + 416) = &MitigationOptionsPolicy::RedirectionTrustPolicy::`vftable';
  *((_QWORD *)this + 422) = 0;
  *((_QWORD *)this + 423) = 0;
  return this;
}

```

## disassembly

```asm
0x180011b90  mov     [rsp-18h+arg_8], rbx
0x180011b95  mov     [rsp-18h+arg_10], rsi
0x180011b9a  push    rbp
0x180011b9b  push    rdi
0x180011b9c  push    r15
0x180011b9e  mov     rbp, rsp
0x180011ba1  sub     rsp, 50h
0x180011ba5  mov     rax, cs:__security_cookie
0x180011bac  xor     rax, rsp
0x180011baf  mov     [rbp+var_8], rax
0x180011bb3  mov     dil, dl
0x180011bb6  mov     rsi, rcx
0x180011bb9  mov     [rbp+var_30], rcx
0x180011bbd  lea     r15, qword_180018390
0x180011bc4  mov     rdx, r15
0x180011bc7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180011bcc  nop
0x180011bcd  mov     rdx, r15
0x180011bd0  lea     rcx, [rbp+var_28]
0x180011bd4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180011bd9  nop
0x180011bda  mov     r8b, dil
0x180011bdd  lea     rdx, [rbp+var_28]
0x180011be1  lea     rcx, [rsi+20h]
0x180011be5  call    ??0Policy@MitigationOptionsPolicy@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; MitigationOptionsPolicy::Policy::Policy(std::wstring const &,bool)
0x180011bea  nop
0x180011beb  lea     rcx, [rbp+var_28]
0x180011bef  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011bf4  lea     rax, ??_7AslrPolicy@MitigationOptionsPolicy@@6B@; const MitigationOptionsPolicy::AslrPolicy::`vftable'
0x180011bfb  mov     [rsi+20h], rax
0x180011bff  xorps   xmm0, xmm0
0x180011c02  xor     eax, eax
0x180011c04  movups  xmmword ptr [rsi+50h], xmm0
0x180011c08  mov     [rsi+60h], rax
0x180011c0c  movups  xmmword ptr [rsi+68h], xmm0
0x180011c10  mov     [rsi+78h], rax
0x180011c14  lea     rbx, [rsi+80h]
0x180011c1b  mov     rdx, r15
0x180011c1e  lea     rcx, [rbp+var_28]
0x180011c22  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180011c27  nop
0x180011c28  mov     r8b, dil
0x180011c2b  lea     rdx, [rbp+var_28]
0x180011c2f  mov     rcx, rbx
0x180011c32  call    ??0Policy@MitigationOptionsPolicy@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; MitigationOptionsPolicy::Policy::Policy(std::wstring const &,bool)
0x180011c37  nop
0x180011c38  lea     rcx, [rbp+var_28]
0x180011c3c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011c41  lea     rax, ??_7DataExecutionPolicy@MitigationOptionsPolicy@@6B@; const MitigationOptionsPolicy::DataExecutionPolicy::`vftable'
0x180011c48  mov     [rbx], rax
0x180011c4b  xor     eax, eax
0x180011c4d  mov     [rbx+30h], rax
0x180011c51  mov     [rbx+38h], rax
0x180011c55  lea     rbx, [rsi+0C0h]
0x180011c5c  mov     rdx, r15
0x180011c5f  lea     rcx, [rbp+var_28]
0x180011c63  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180011c68  nop
0x180011c69  mov     r8b, dil
0x180011c6c  lea     rdx, [rbp+var_28]
0x180011c70  mov     rcx, rbx
0x180011c73  call    ??0Policy@MitigationOptionsPolicy@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; MitigationOptionsPolicy::Policy::Policy(std::wstring const &,bool)
0x180011c78  nop
0x180011c79  lea     rcx, [rbp+var_28]
0x180011c7d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011c82  lea     rax, ??_7HandlePolicy@MitigationOptionsPolicy@@6B@; const MitigationOptionsPolicy::HandlePolicy::`vftable'
0x180011c89  mov     [rbx], rax
0x180011c8c  xor     eax, eax
0x180011c8e  mov     [rbx+30h], rax
0x180011c92  mov     [rbx+38h], rax
0x180011c96  lea     rbx, [rsi+100h]
0x180011c9d  mov     rdx, r15
0x180011ca0  lea     rcx, [rbp+var_28]
0x180011ca4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180011ca9  nop
0x180011caa  mov     r8b, dil
0x180011cad  lea     rdx, [rbp+var_28]
0x180011cb1  mov     rcx, rbx
0x180011cb4  call    ??0Policy@MitigationOptionsPolicy@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; MitigationOptionsPolicy::Policy::Policy(std::wstring const &,bool)
0x180011cb9  nop
0x180011cba  lea     rcx, [rbp+var_28]
0x180011cbe  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011cc3  lea     rax, ??_7SysCallPolicy@MitigationOptionsPolicy@@6B@; const MitigationOptionsPolicy::SysCallPolicy::`vftable'
0x180011cca  mov     [rbx], rax
0x180011ccd  xorps   xmm0, xmm0
0x180011cd0  movups  xmmword ptr [rbx+30h], xmm0
0x180011cd4  xorps   xmm1, xmm1
0x180011cd7  movups  xmmword ptr [rbx+40h], xmm1
0x180011cdb  lea     rbx, [rsi+150h]
0x180011ce2  mov     rdx, r15
0x180011ce5  lea     rcx, [rbp+var_28]
0x180011ce9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180011cee  nop
0x180011cef  mov     r8b, dil
0x180011cf2  lea     rdx, [rbp+var_28]
0x180011cf6  mov     rcx, rbx
0x180011cf9  call    ??0Policy@MitigationOptionsPolicy@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; MitigationOptionsPolicy::Policy::Policy(std::wstring const &,bool)
0x180011cfe  nop
0x180011cff  lea     rcx, [rbp+var_28]
0x180011d03  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011d08  lea     rax, ??_7ExtensionPointPolicy@MitigationOptionsPolicy@@6B@; const MitigationOptionsPolicy::ExtensionPointPolicy::`vftable'
0x180011d0f  mov     [rbx], rax
0x180011d12  xor     eax, eax
0x180011d14  mov     [rbx+30h], rax
0x180011d18  mov     [rbx+38h], rax
0x180011d1c  lea     rbx, [rsi+190h]
0x180011d23  mov     rdx, r15
0x180011d26  lea     rcx, [rbp+var_28]
0x180011d2a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180011d2f  nop
0x180011d30  mov     r8b, dil
0x180011d33  lea     rdx, [rbp+var_28]
0x180011d37  mov     rcx, rbx
0x180011d3a  call    ??0Policy@MitigationOptionsPolicy@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; MitigationOptionsPolicy::Policy::Policy(std::wstring const &,bool)
0x180011d3f  nop
0x180011d40  lea     rcx, [rbp+var_28]
0x180011d44  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011d49  lea     rax, ??_7DynamicCodePolicy@MitigationOptionsPolicy@@6B@; const MitigationOptionsPolicy::DynamicCodePolicy::`vftable'
0x180011d50  mov     [rbx], rax
0x180011d53  xor     eax, eax
0x180011d55  mov     [rbx+30h], rax
0x180011d59  mov     [rbx+38h], rax
0x180011d5d  lea     rbx, [rsi+1D0h]
0x180011d64  mov     rdx, r15
0x180011d67  lea     rcx, [rbp+var_28]
0x180011d6b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180011d70  nop
0x180011d71  mov     r8b, dil
0x180011d74  lea     rdx, [rbp+var_28]
0x180011d78  mov     rcx, rbx
0x180011d7b  call    ??0Policy@MitigationOptionsPolicy@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; MitigationOptionsPolicy::Policy::Policy(std::wstring const &,bool)
0x180011d80  nop
0x180011d81  lea     rcx, [rbp+var_28]
0x180011d85  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011d8a  lea     rax, ??_7ControlFlowGuardPolicy@MitigationOptionsPolicy@@6B@; const MitigationOptionsPolicy::ControlFlowGuardPolicy::`vftable'
0x180011d91  mov     [rbx], rax
0x180011d94  xorps   xmm0, xmm0
0x180011d97  movups  xmmword ptr [rbx+30h], xmm0
0x180011d9b  xorps   xmm1, xmm1
0x180011d9e  movups  xmmword ptr [rbx+40h], xmm1
0x180011da2  lea     rbx, [rsi+220h]
0x180011da9  mov     rdx, r15
0x180011dac  lea     rcx, [rbp+var_28]
0x180011db0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180011db5  nop
0x180011db6  mov     r8b, dil
0x180011db9  lea     rdx, [rbp+var_28]
0x180011dbd  mov     rcx, rbx
0x180011dc0  call    ??0Policy@MitigationOptionsPolicy@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; MitigationOptionsPolicy::Policy::Policy(std::wstring const &,bool)
0x180011dc5  nop
0x180011dc6  lea     rcx, [rbp+var_28]
0x180011dca  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011dcf  lea     rax, ??_7BinarySigningPolicy@MitigationOptionsPolicy@@6B@; const MitigationOptionsPolicy::BinarySigningPolicy::`vftable'
0x180011dd6  mov     [rbx], rax
0x180011dd9  xorps   xmm0, xmm0
0x180011ddc  movups  xmmword ptr [rbx+30h], xmm0
0x180011de0  xorps   xmm1, xmm1
0x180011de3  movups  xmmword ptr [rbx+40h], xmm1
0x180011de7  lea     rbx, [rsi+270h]
0x180011dee  mov     rdx, r15
0x180011df1  lea     rcx, [rbp+var_28]
0x180011df5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180011dfa  nop
0x180011dfb  mov     r8b, dil
0x180011dfe  lea     rdx, [rbp+var_28]
0x180011e02  mov     rcx, rbx
0x180011e05  call    ??0Policy@MitigationOptionsPolicy@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; MitigationOptionsPolicy::Policy::Policy(std::wstring const &,bool)
0x180011e0a  nop
0x180011e0b  lea     rcx, [rbp+var_28]
0x180011e0f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011e14  lea     rax, ??_7FontPolicy@MitigationOptionsPolicy@@6B@; const MitigationOptionsPolicy::FontPolicy::`vftable'
0x180011e1b  mov     [rbx], rax
0x180011e1e  xor     eax, eax
0x180011e20  mov     [rbx+30h], rax
0x180011e24  mov     [rbx+38h], rax
0x180011e28  lea     rbx, [rsi+2B0h]
0x180011e2f  mov     rdx, r15
0x180011e32  lea     rcx, [rbp+var_28]
0x180011e36  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180011e3b  nop
0x180011e3c  mov     r8b, dil
0x180011e3f  lea     rdx, [rbp+var_28]
0x180011e43  mov     rcx, rbx
0x180011e46  call    ??0Policy@MitigationOptionsPolicy@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; MitigationOptionsPolicy::Policy::Policy(std::wstring const &,bool)
0x180011e4b  nop
0x180011e4c  lea     rcx, [rbp+var_28]
0x180011e50  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011e55  lea     rax, ??_7ImageLoadPolicy@MitigationOptionsPolicy@@6B@; const MitigationOptionsPolicy::ImageLoadPolicy::`vftable'
0x180011e5c  mov     [rbx], rax
0x180011e5f  xorps   xmm0, xmm0
0x180011e62  xor     eax, eax
0x180011e64  movups  xmmword ptr [rbx+30h], xmm0
0x180011e68  mov     [rbx+40h], rax
0x180011e6c  movups  xmmword ptr [rbx+48h], xmm0
0x180011e70  mov     [rbx+58h], rax
0x180011e74  lea     rbx, [rsi+310h]
0x180011e7b  mov     rdx, r15
0x180011e7e  lea     rcx, [rbp+var_28]
0x180011e82  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180011e87  nop
0x180011e88  mov     r8b, dil
0x180011e8b  lea     rdx, [rbp+var_28]
0x180011e8f  mov     rcx, rbx
0x180011e92  call    ??0Policy@MitigationOptionsPolicy@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; MitigationOptionsPolicy::Policy::Policy(std::wstring const &,bool)
0x180011e97  nop
0x180011e98  lea     rcx, [rbp+var_28]
0x180011e9c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011ea1  lea     rax, ??_7PayloadRestrictionPolicy@MitigationOptionsPolicy@@6B@; const MitigationOptionsPolicy::PayloadRestrictionPolicy::`vftable'
0x180011ea8  mov     [rbx], rax
0x180011eab  lea     rcx, [rbx+30h]; void *
0x180011eaf  xor     edx, edx; Val
0x180011eb1  mov     r8d, 430h; Size
0x180011eb7  call    memset_0
0x180011ebc  lea     rcx, [rbx+460h]; void *
0x180011ec3  xor     edx, edx; Val
0x180011ec5  mov     r8d, 430h; Size
0x180011ecb  call    memset_0
0x180011ed0  nop
0x180011ed1  lea     rbx, [rsi+0BA0h]
0x180011ed8  mov     rdx, r15
0x180011edb  lea     rcx, [rbp+var_28]
0x180011edf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180011ee4  nop
0x180011ee5  mov     r8b, dil
0x180011ee8  lea     rdx, [rbp+var_28]
0x180011eec  mov     rcx, rbx
0x180011eef  call    ??0Policy@MitigationOptionsPolicy@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; MitigationOptionsPolicy::Policy::Policy(std::wstring const &,bool)
0x180011ef4  nop
0x180011ef5  lea     rcx, [rbp+var_28]
0x180011ef9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011efe  lea     rax, ??_7SehopPolicy@MitigationOptionsPolicy@@6B@; const MitigationOptionsPolicy::SehopPolicy::`vftable'
0x180011f05  mov     [rbx], rax
0x180011f08  xor     eax, eax
0x180011f0a  mov     [rbx+30h], rax
0x180011f0e  mov     [rbx+38h], rax
0x180011f12  lea     rbx, [rsi+0BE0h]
0x180011f19  mov     rdx, r15
0x180011f1c  lea     rcx, [rbp+var_28]
0x180011f20  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180011f25  nop
0x180011f26  mov     r8b, dil
0x180011f29  lea     rdx, [rbp+var_28]
0x180011f2d  mov     rcx, rbx
0x180011f30  call    ??0Policy@MitigationOptionsPolicy@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; MitigationOptionsPolicy::Policy::Policy(std::wstring const &,bool)
0x180011f35  nop
0x180011f36  lea     rcx, [rbp+var_28]
0x180011f3a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011f3f  lea     rax, ??_7HeapPolicy@MitigationOptionsPolicy@@6B@; const MitigationOptionsPolicy::HeapPolicy::`vftable'
0x180011f46  mov     [rbx], rax
0x180011f49  xor     eax, eax
0x180011f4b  mov     [rbx+30h], rax
0x180011f4f  mov     [rbx+38h], rax
0x180011f53  lea     rbx, [rsi+0C20h]
0x180011f5a  mov     rdx, r15
0x180011f5d  lea     rcx, [rbp+var_28]
0x180011f61  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180011f66  nop
0x180011f67  mov     r8b, dil
0x180011f6a  lea     rdx, [rbp+var_28]
0x180011f6e  mov     rcx, rbx
0x180011f71  call    ??0Policy@MitigationOptionsPolicy@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; MitigationOptionsPolicy::Policy::Policy(std::wstring const &,bool)
0x180011f76  nop
0x180011f77  lea     rcx, [rbp+var_28]
0x180011f7b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011f80  lea     rax, ??_7ChildProcessPolicy@MitigationOptionsPolicy@@6B@; const MitigationOptionsPolicy::ChildProcessPolicy::`vftable'
0x180011f87  mov     [rbx], rax
0x180011f8a  xor     eax, eax
0x180011f8c  mov     [rbx+30h], rax
0x180011f90  mov     [rbx+38h], rax
0x180011f94  lea     rbx, [rsi+0C60h]
0x180011f9b  mov     rdx, r15
0x180011f9e  lea     rcx, [rbp+var_28]
0x180011fa2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180011fa7  nop
0x180011fa8  mov     r8b, dil
0x180011fab  lea     rdx, [rbp+var_28]
0x180011faf  mov     rcx, rbx
0x180011fb2  call    ??0Policy@MitigationOptionsPolicy@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; MitigationOptionsPolicy::Policy::Policy(std::wstring const &,bool)
0x180011fb7  nop
0x180011fb8  lea     rcx, [rbp+var_28]
0x180011fbc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011fc1  lea     rax, ??_7UserShadowStackPolicy@MitigationOptionsPolicy@@6B@; const MitigationOptionsPolicy::UserShadowStackPolicy::`vftable'
0x180011fc8  mov     [rbx], rax
0x180011fcb  xorps   xmm0, xmm0
0x180011fce  xor     eax, eax
0x180011fd0  movups  xmmword ptr [rbx+30h], xmm0
0x180011fd4  mov     [rbx+40h], rax
0x180011fd8  movups  xmmword ptr [rbx+48h], xmm0
0x180011fdc  mov     [rbx+58h], rax
0x180011fe0  lea     rbx, [rsi+0CC0h]
0x180011fe7  mov     rdx, r15
0x180011fea  lea     rcx, [rbp+var_28]
0x180011fee  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180011ff3  nop
0x180011ff4  mov     r8b, dil
0x180011ff7  lea     rdx, [rbp+var_28]
0x180011ffb  mov     rcx, rbx
0x180011ffe  call    ??0Policy@MitigationOptionsPolicy@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; MitigationOptionsPolicy::Policy::Policy(std::wstring const &,bool)
0x180012003  nop
0x180012004  lea     rcx, [rbp+var_28]
  ... truncated ...
```
