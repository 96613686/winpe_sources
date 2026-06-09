# Windows::Foundation::Uri::Uri(Platform::String *)

- ea: `0x1400149a4`
- end: `0x140014aa3`
- name: `??0Uri@Foundation@Windows@@QE$AAA@PE$AAVString@Platform@@@Z`
- size: `255`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140015f1c`
- `0x14002bad0`

## callees

- `0x14000285c`
- `0x1400086b0`
- `0x1400149a4`
- `0x140017334`
- `0x140031960`
- `0x140035010`

## string_xrefs

- `0x1400149ee`: `Windows.Foundation.Uri`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Foundation::Uri::Uri(__int64 a1, __int64 a2, __int64 a3, void **a4)
{
  int ActivationFactoryByPCWSTR; // eax
  __int64 v6; // rax
  __int64 v7; // rbx
  __int64 v9; // [rsp+28h] [rbp-28h] BYREF
  _DWORD v10[4]; // [rsp+30h] [rbp-20h] BYREF

  v10[0] = 1151957359;
  v10[1] = 1340043838;
  v10[2] = 1040390306;
  v10[3] = -2067746699;
  v9 = 0;
  ActivationFactoryByPCWSTR = __winRT::__getActivationFactoryByPCWSTR(
                                (__winRT *)L"Windows.Foundation.Uri",
                                v10,
                                (struct Platform::Guid *)&v9,
                                a4);
  if ( ActivationFactoryByPCWSTR < 0 )
    __abi_WinRTraiseException(ActivationFactoryByPCWSTR);
  v6 = Windows::Foundation::Collections::IMap<Platform::String __gc *,Platform::Object __gc *>::Lookup(v9, a2);
  v7 = v6;
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  }
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  return v7;
}

```

## disassembly

```asm
0x1400149a4  mov     [rsp-8+arg_0], rbx
0x1400149a9  push    rbp
0x1400149aa  mov     rbp, rsp
0x1400149ad  sub     rsp, 50h
0x1400149b1  mov     rax, cs:__security_cookie
0x1400149b8  xor     rax, rsp
0x1400149bb  mov     [rbp+var_10], rax
0x1400149bf  mov     rbx, rdx
0x1400149c2  mov     [rbp+var_20], 44A9796Fh
0x1400149c9  mov     [rbp+var_1C], 4FDF723Eh
0x1400149d0  mov     [rbp+var_18], 3E0318A2h
0x1400149d7  mov     [rbp+var_14], 84C0B075h
0x1400149de  mov     [rbp+var_28], 0
0x1400149e6  lea     r8, [rbp+var_28]; struct Platform::Guid *
0x1400149ea  lea     rdx, [rbp+var_20]; void *
0x1400149ee  lea     rcx, aWindowsFoundat_8; "Windows.Foundation.Uri"
0x1400149f5  call    ?__getActivationFactoryByPCWSTR@__winRT@@YAJPEAXAEAVGuid@Platform@@PEAPEAX@Z; __winRT::__getActivationFactoryByPCWSTR(void *,Platform::Guid &,void * *)
0x1400149fa  test    eax, eax
0x1400149fc  js      loc_140014A9B
0x140014a02  mov     rdx, rbx
0x140014a05  mov     rcx, [rbp+var_28]
0x140014a09  call    ?Lookup@?$IMap@PE$AAVString@Platform@@PE$AAVObject@2@@Collections@Foundation@Windows@@UE$AAAPE$AAVObject@Platform@@PE$AAVString@6@@Z; Windows::Foundation::Collections::IMap<Platform::String *,Platform::Object *>::Lookup(Platform::String *)
0x140014a0e  mov     rbx, rax
0x140014a11  mov     [rbp+var_30], rax
0x140014a15  test    rax, rax
0x140014a18  jz      short loc_140014A29
0x140014a1a  mov     rcx, [rax]
0x140014a1d  mov     rax, [rcx+8]
0x140014a21  mov     rcx, rbx
0x140014a24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014a29  mov     [rbp+var_30], rbx
0x140014a2d  test    rbx, rbx
0x140014a30  jz      short loc_140014A42
0x140014a32  mov     rax, [rbx]
0x140014a35  mov     rcx, rbx
0x140014a38  mov     rax, [rax+10h]
0x140014a3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014a41  nop
0x140014a42  test    rbx, rbx
0x140014a45  jz      short loc_140014A57
0x140014a47  mov     rax, [rbx]
0x140014a4a  mov     rcx, rbx
0x140014a4d  mov     rax, [rax+8]
0x140014a51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014a56  nop
0x140014a57  test    rbx, rbx
0x140014a5a  jz      short loc_140014A6C
0x140014a5c  mov     rax, [rbx]
0x140014a5f  mov     rcx, rbx
0x140014a62  mov     rax, [rax+10h]
0x140014a66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014a6b  nop
0x140014a6c  mov     rcx, [rbp+var_28]
0x140014a70  test    rcx, rcx
0x140014a73  jz      short loc_140014A81
0x140014a75  mov     rax, [rcx]
0x140014a78  mov     rax, [rax+10h]
0x140014a7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014a81  mov     rax, rbx
0x140014a84  mov     rcx, [rbp+var_10]
0x140014a88  xor     rcx, rsp; StackCookie
0x140014a8b  call    __security_check_cookie
0x140014a90  mov     rbx, [rsp+50h+arg_0]
0x140014a95  add     rsp, 50h
0x140014a99  pop     rbp
0x140014a9a  retn
0x140014a9b  mov     ecx, eax; int
0x140014a9d  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
```
