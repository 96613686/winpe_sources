# CDeleteDirectoriesJob::ToString(void)

- ea: `0x180013950`
- end: `0x180013a93`
- name: `?ToString@CDeleteDirectoriesJob@@UEBAPEAVString@UnBCL@@XZ`
- size: `323`
- prototype: `struct UnBCL::String *__fastcall(CDeleteDirectoriesJob *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x18000464c`
- `0x1800066dc`
- `0x180013950`
- `0x180036010`

## import_xrefs

- `unbcl!?ToString@StringBuilder@UnBCL@@UEBAPEAVString@2@XZ` at `0x1800139f6`
- `unbcl!?ToString@StringBuilder@UnBCL@@UEBAPEAVString@2@XZ` at `0x1800139f6`
- `unbcl!?Append@StringBuilder@UnBCL@@QEAAPEAV12@PEBVString@2@@Z` at `0x1800139d9`
- `unbcl!?Append@StringBuilder@UnBCL@@QEAAPEAV12@PEBVString@2@@Z` at `0x1800139d9`
- `unbcl!?Append@StringBuilder@UnBCL@@QEAAPEAV12@PEBG@Z` at `0x180013976`
- `unbcl!?Append@StringBuilder@UnBCL@@QEAAPEAV12@PEBG@Z` at `0x1800139ea`
- `unbcl!?Append@StringBuilder@UnBCL@@QEAAPEAV12@PEBG@Z` at `0x180013976`
- `unbcl!?Append@StringBuilder@UnBCL@@QEAAPEAV12@PEBG@Z` at `0x1800139ea`
- `unbcl!??1StringBuilder@UnBCL@@UEAA@XZ` at `0x180013a7c`
- `unbcl!??1StringBuilder@UnBCL@@UEAA@XZ` at `0x180013a7c`
- `unbcl!??0StringBuilder@UnBCL@@QEAA@XZ` at `0x180013964`
- `unbcl!??0StringBuilder@UnBCL@@QEAA@XZ` at `0x180013964`
- `unbcl!?TrimEnd@String@UnBCL@@QEBAPEAV12@PEBG@Z` at `0x180013a1e`
- `unbcl!?TrimEnd@String@UnBCL@@QEBAPEAV12@PEBG@Z` at `0x180013a1e`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x180013980`
- `unbcl!??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ` at `0x180013980`
- `unbcl!?Steal@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAPEAVString@2@XZ` at `0x180013a4f`
- `unbcl!?Steal@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAPEAVString@2@XZ` at `0x180013a4f`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180013a3a`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180013a3a`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180013a0e`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180013a0e`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180013a45`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180013a5c`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180013a45`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180013a5c`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180013a03`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180013a2b`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180013a03`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180013a2b`

## string_xrefs

- `0x18001396b`: `DeleteDirectories: `

## pseudocode

```c
// Hidden C++ exception states: #wind=4
struct UnBCL::String *__fastcall CDeleteDirectoriesJob::ToString(CDeleteDirectoriesJob *this)
{
  __int64 v2; // rax
  __int64 (__fastcall ***v3)(_QWORD); // rcx
  __int64 v4; // rax
  __int64 v5; // rbx
  const struct UnBCL::String *v6; // rax
  struct UnBCL::String *v7; // rax
  UnBCL::String *v8; // rax
  struct UnBCL::String *v9; // rax
  __int64 v10; // rbx
  _BYTE v12[16]; // [rsp+20h] [rbp-50h] BYREF
  _QWORD v13[2]; // [rsp+30h] [rbp-40h] BYREF
  _BYTE v14[16]; // [rsp+40h] [rbp-30h] BYREF
  _BYTE v15[32]; // [rsp+50h] [rbp-20h] BYREF

  UnBCL::StringBuilder::StringBuilder((UnBCL::StringBuilder *)v15);
  UnBCL::StringBuilder::Append((UnBCL::StringBuilder *)v15, L"DeleteDirectories: ");
  v2 = UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->((char *)this + 16);
  v3 = (__int64 (__fastcall ***)(_QWORD))(*(int *)(*(_QWORD *)(v2 + 8) + 8LL) + v2 + 8);
  v4 = (**v3)(v3);
  UnBCL::SmartPtr<UnBCL::IEnumerator<UnBCL::String *>>::SmartPtr<UnBCL::IEnumerator<UnBCL::String *>>(v13, v4);
  v5 = v13[1];
  while ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5) )
  {
    v6 = (const struct UnBCL::String *)(**(__int64 (__fastcall ***)(__int64))v5)(v5);
    UnBCL::StringBuilder::Append((UnBCL::StringBuilder *)v15, v6);
    UnBCL::StringBuilder::Append((UnBCL::StringBuilder *)v15, L", ");
  }
  v7 = UnBCL::StringBuilder::ToString((UnBCL::StringBuilder *)v15);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v12, v7);
  v8 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v12);
  v9 = UnBCL::String::TrimEnd(v8, L", ");
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v14, v9);
  UnBCL::SmartPtr<UnBCL::String>::operator=(v12, v14);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v14);
  v10 = UnBCL::SmartPtr<UnBCL::String>::Steal(v12);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v12);
  v13[0] = &UnBCL::SmartPtr<UnBCL::IEnumerator<UnBCL::String *>>::`vftable';
  UnBCL::SmartPtr<UnBCL::IEnumerator<ISetupCleanupJob *>>::DeAssign((__int64)v13);
  UnBCL::StringBuilder::~StringBuilder((UnBCL::StringBuilder *)v15);
  return (struct UnBCL::String *)v10;
}

```

## disassembly

```asm
0x180013950  mov     [rsp-8+arg_0], rbx
0x180013955  push    rbp
0x180013956  mov     rbp, rsp
0x180013959  sub     rsp, 70h
0x18001395d  mov     rbx, rcx
0x180013960  lea     rcx, [rbp+var_20]
0x180013964  call    cs:__imp_??0StringBuilder@UnBCL@@QEAA@XZ; UnBCL::StringBuilder::StringBuilder(void)
0x18001396a  nop
0x18001396b  lea     rdx, aDeletedirector_0; "DeleteDirectories: "
0x180013972  lea     rcx, [rbp+var_20]
0x180013976  call    cs:__imp_?Append@StringBuilder@UnBCL@@QEAAPEAV12@PEBG@Z; UnBCL::StringBuilder::Append(ushort const *)
0x18001397c  lea     rcx, [rbx+10h]
0x180013980  call    cs:__imp_??C?$SmartPtr@V?$ArrayList@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$ArrayList@PEAVString@UnBCL@@@1@XZ; UnBCL::SmartPtr<UnBCL::ArrayList<UnBCL::String *>>::operator->(void)
0x180013986  mov     rcx, [rax+8]
0x18001398a  movsxd  rdx, dword ptr [rcx+8]
0x18001398e  lea     rcx, [rax+8]
0x180013992  add     rcx, rdx
0x180013995  mov     rax, [rcx]
0x180013998  mov     rax, [rax]
0x18001399b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800139a0  mov     rdx, rax
0x1800139a3  lea     rcx, [rbp+var_40]
0x1800139a7  call    ??0?$SmartPtr@U?$IEnumerator@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAU?$IEnumerator@PEAVString@UnBCL@@@1@@Z; UnBCL::SmartPtr<UnBCL::IEnumerator<UnBCL::String *>>::SmartPtr<UnBCL::IEnumerator<UnBCL::String *>>(UnBCL::IEnumerator<UnBCL::String *> *)
0x1800139ac  nop
0x1800139ad  mov     rbx, [rbp+var_38]
0x1800139b1  mov     rax, [rbx]
0x1800139b4  mov     rcx, rbx
0x1800139b7  mov     rax, [rax+8]
0x1800139bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800139c0  test    eax, eax
0x1800139c2  jz      short loc_1800139F2
0x1800139c4  mov     rax, [rbx]
0x1800139c7  mov     rcx, rbx
0x1800139ca  mov     rax, [rax]
0x1800139cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800139d2  mov     rdx, rax
0x1800139d5  lea     rcx, [rbp+var_20]
0x1800139d9  call    cs:__imp_?Append@StringBuilder@UnBCL@@QEAAPEAV12@PEBVString@2@@Z; UnBCL::StringBuilder::Append(UnBCL::String const *)
0x1800139df  lea     rdx, asc_18003DFE0; ", "
0x1800139e6  lea     rcx, [rbp+var_20]
0x1800139ea  call    cs:__imp_?Append@StringBuilder@UnBCL@@QEAAPEAV12@PEBG@Z; UnBCL::StringBuilder::Append(ushort const *)
0x1800139f0  jmp     short loc_1800139B1
0x1800139f2  lea     rcx, [rbp+var_20]
0x1800139f6  call    cs:__imp_?ToString@StringBuilder@UnBCL@@UEBAPEAVString@2@XZ; UnBCL::StringBuilder::ToString(void)
0x1800139fc  mov     rdx, rax
0x1800139ff  lea     rcx, [rbp+var_50]
0x180013a03  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180013a09  nop
0x180013a0a  lea     rcx, [rbp+var_50]
0x180013a0e  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180013a14  lea     rdx, asc_18003DFE0; ", "
0x180013a1b  mov     rcx, rax
0x180013a1e  call    cs:__imp_?TrimEnd@String@UnBCL@@QEBAPEAV12@PEBG@Z; UnBCL::String::TrimEnd(ushort const *)
0x180013a24  mov     rdx, rax
0x180013a27  lea     rcx, [rbp+var_30]
0x180013a2b  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180013a31  nop
0x180013a32  lea     rdx, [rbp+var_30]
0x180013a36  lea     rcx, [rbp+var_50]
0x180013a3a  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x180013a40  nop
0x180013a41  lea     rcx, [rbp+var_30]
0x180013a45  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180013a4b  lea     rcx, [rbp+var_50]
0x180013a4f  call    cs:__imp_?Steal@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::Steal(void)
0x180013a55  mov     rbx, rax
0x180013a58  lea     rcx, [rbp+var_50]
0x180013a5c  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180013a62  nop
0x180013a63  lea     rax, ??_7?$SmartPtr@U?$IEnumerator@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::IEnumerator<UnBCL::String *>>::`vftable'
0x180013a6a  mov     [rbp+var_40], rax
0x180013a6e  lea     rcx, [rbp+var_40]
0x180013a72  call    ?DeAssign@?$SmartPtr@U?$IEnumerator@PEAVISetupCleanupJob@@@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::IEnumerator<ISetupCleanupJob *>>::DeAssign(void)
0x180013a77  nop
0x180013a78  lea     rcx, [rbp+var_20]
0x180013a7c  call    cs:__imp_??1StringBuilder@UnBCL@@UEAA@XZ; UnBCL::StringBuilder::~StringBuilder(void)
0x180013a82  mov     rax, rbx
0x180013a85  mov     rbx, [rsp+70h+arg_0]
0x180013a8d  add     rsp, 70h
0x180013a91  pop     rbp
0x180013a92  retn
```
