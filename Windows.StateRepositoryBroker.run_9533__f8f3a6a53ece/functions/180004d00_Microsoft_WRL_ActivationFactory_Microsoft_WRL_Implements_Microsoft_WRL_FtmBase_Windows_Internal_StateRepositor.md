# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::StateRepository::IPackageResourceResolverStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetIids(ulong *,_GUID * *)

- ea: `0x180004d00`
- end: `0x180004d5f`
- name: `?GetIids@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIPackageResourceResolverStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004d70`

## callees

- `0x1800047cc`
- `0x180004d00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004d22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004d22`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::StateRepository::IPackageResourceResolverStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetIids(
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
  v6 = CoTaskMemAlloc(0x20u);
  if ( !v6 )
    return 2147942414LL;
  v9 = 0;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::StateRepository::IPackageResourceResolverStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::FillArrayWithIid(
    v5,
    &v9,
    v6);
  *a2 = 2;
  result = 0;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x180004d00  mov     [rsp+arg_0], rbx
0x180004d05  push    rdi
0x180004d06  sub     rsp, 20h
0x180004d0a  mov     qword ptr [r8], 0
0x180004d11  mov     ecx, 20h ; ' '; cb
0x180004d16  mov     dword ptr [rdx], 0
0x180004d1c  mov     rbx, r8
0x180004d1f  mov     rdi, rdx
0x180004d22  call    cs:__imp_CoTaskMemAlloc
0x180004d28  mov     r8, rax
0x180004d2b  test    rax, rax
0x180004d2e  jnz     short loc_180004D37
0x180004d30  mov     eax, 8007000Eh
0x180004d35  jmp     short loc_180004D54
0x180004d37  lea     rdx, [rsp+28h+arg_8]
0x180004d3c  mov     [rsp+28h+arg_8], 0
0x180004d44  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@UIActivationFactory@@U?$Implements@VFtmBase@WRL@Microsoft@@UIPackageResourceResolverStatics@StateRepository@Internal@Windows@@@23@VNil@Details@23@V6723@V6723@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::StateRepository::IPackageResourceResolverStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::FillArrayWithIid(ulong *,_GUID *)
0x180004d49  mov     dword ptr [rdi], 2
0x180004d4f  xor     eax, eax
0x180004d51  mov     [rbx], r8
0x180004d54  mov     rbx, [rsp+28h+arg_0]
0x180004d59  add     rsp, 20h
0x180004d5d  pop     rdi
0x180004d5e  retn
```
