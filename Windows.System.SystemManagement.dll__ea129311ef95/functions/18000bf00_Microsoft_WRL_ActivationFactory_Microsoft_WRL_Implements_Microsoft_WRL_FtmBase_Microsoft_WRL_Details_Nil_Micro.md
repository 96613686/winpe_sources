# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetIids(ulong *,_GUID * *)

- ea: `0x18000bf00`
- end: `0x18000bf5f`
- name: `?GetIids@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@VNil@Details@23@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000bca4`
- `0x18000bf00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000bf22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000bf22`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetIids(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  __int64 v5; // rcx
  LPVOID v6; // r8
  __int64 result; // rax
  __int64 v8; // r8
  int v9; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v6 = CoTaskMemAlloc(0x10u);
  if ( !v6 )
    return 2147942414LL;
  v9 = 0;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::FillArrayWithIid(
    v5,
    &v9,
    v6);
  *a2 = 1;
  result = 0;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x18000bf00  mov     [rsp+arg_0], rbx
0x18000bf05  push    rdi
0x18000bf06  sub     rsp, 20h
0x18000bf0a  mov     qword ptr [r8], 0
0x18000bf11  mov     ecx, 10h; cb
0x18000bf16  mov     dword ptr [rdx], 0
0x18000bf1c  mov     rbx, r8
0x18000bf1f  mov     rdi, rdx
0x18000bf22  call    cs:__imp_CoTaskMemAlloc
0x18000bf28  mov     r8, rax
0x18000bf2b  test    rax, rax
0x18000bf2e  jnz     short loc_18000BF37
0x18000bf30  mov     eax, 8007000Eh
0x18000bf35  jmp     short loc_18000BF54
0x18000bf37  lea     rdx, [rsp+28h+arg_8]
0x18000bf3c  mov     [rsp+28h+arg_8], 0
0x18000bf44  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@UIActivationFactory@@U?$Implements@VFtmBase@WRL@Microsoft@@VNil@Details@23@@23@VNil@Details@23@V6723@V6723@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::FillArrayWithIid(ulong *,_GUID *)
0x18000bf49  mov     dword ptr [rdi], 1
0x18000bf4f  xor     eax, eax
0x18000bf51  mov     [rbx], r8
0x18000bf54  mov     rbx, [rsp+28h+arg_0]
0x18000bf59  add     rsp, 20h
0x18000bf5d  pop     rdi
0x18000bf5e  retn
```
