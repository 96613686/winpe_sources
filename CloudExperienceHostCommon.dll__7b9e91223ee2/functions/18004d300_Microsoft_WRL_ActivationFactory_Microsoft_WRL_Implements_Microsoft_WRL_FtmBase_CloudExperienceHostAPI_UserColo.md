# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,CloudExperienceHostAPI::UserColorPreference::IUserPreferredColorsStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetIids(ulong *,_GUID * *)

- ea: `0x18004d300`
- end: `0x18004d35f`
- name: `?GetIids@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIUserPreferredColorsStatics@UserColorPreference@CloudExperienceHostAPI@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004d370`

## callees

- `0x18004d2b4`
- `0x18004d300`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004d322`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004d322`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,CloudExperienceHostAPI::UserColorPreference::IUserPreferredColorsStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetIids(
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
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,CloudExperienceHostAPI::UserColorPreference::IUserPreferredColorsStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::FillArrayWithIid(
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
0x18004d300  mov     [rsp+arg_0], rbx
0x18004d305  push    rdi
0x18004d306  sub     rsp, 20h
0x18004d30a  mov     qword ptr [r8], 0
0x18004d311  mov     ecx, 20h ; ' '; cb
0x18004d316  mov     dword ptr [rdx], 0
0x18004d31c  mov     rbx, r8
0x18004d31f  mov     rdi, rdx
0x18004d322  call    cs:__imp_CoTaskMemAlloc
0x18004d328  mov     r8, rax
0x18004d32b  test    rax, rax
0x18004d32e  jnz     short loc_18004D337
0x18004d330  mov     eax, 8007000Eh
0x18004d335  jmp     short loc_18004D354
0x18004d337  lea     rdx, [rsp+28h+arg_8]
0x18004d33c  mov     [rsp+28h+arg_8], 0
0x18004d344  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@UIActivationFactory@@U?$Implements@VFtmBase@WRL@Microsoft@@UIUserPreferredColorsStatics@UserColorPreference@CloudExperienceHostAPI@@@23@VNil@Details@23@V6723@V6723@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,CloudExperienceHostAPI::UserColorPreference::IUserPreferredColorsStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::FillArrayWithIid(ulong *,_GUID *)
0x18004d349  mov     dword ptr [rdi], 2
0x18004d34f  xor     eax, eax
0x18004d351  mov     [rbx], r8
0x18004d354  mov     rbx, [rsp+28h+arg_0]
0x18004d359  add     rsp, 20h
0x18004d35d  pop     rdi
0x18004d35e  retn
```
