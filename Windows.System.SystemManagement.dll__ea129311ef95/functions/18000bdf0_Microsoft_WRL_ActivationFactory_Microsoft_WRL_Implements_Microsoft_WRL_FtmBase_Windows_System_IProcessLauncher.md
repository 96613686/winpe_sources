# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::System::IProcessLauncherStatics>,IInspectable,Microsoft::WRL::Details::Nil,0>::GetIids(ulong *,_GUID * *)

- ea: `0x18000bdf0`
- end: `0x18000be5a`
- name: `?GetIids@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIProcessLauncherStatics@System@Windows@@@WRL@Microsoft@@UIInspectable@@VNil@Details@23@$0A@@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `106`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000be60`
- `0x18000be70`

## callees

- `0x18000bc74`
- `0x18000bdf0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000be12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000be12`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::System::IProcessLauncherStatics>,IInspectable,Microsoft::WRL::Details::Nil,0>::GetIids(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  GUID *v5; // rax
  __int64 v6; // rcx
  __int64 result; // rax
  __int64 v8; // r8
  int v9; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x30u);
  if ( !v5 )
    return 2147942414LL;
  v9 = 1;
  *v5 = GUID_00000035_0000_0000_c000_000000000046;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::System::IProcessLauncherStatics>>,IInspectable,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::FillArrayWithIid(
    v6,
    &v9,
    v5);
  *a2 = 3;
  result = 0;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x18000bdf0  mov     [rsp+arg_0], rbx
0x18000bdf5  push    rdi
0x18000bdf6  sub     rsp, 20h
0x18000bdfa  mov     qword ptr [r8], 0
0x18000be01  mov     ecx, 30h ; '0'; cb
0x18000be06  mov     dword ptr [rdx], 0
0x18000be0c  mov     rbx, r8
0x18000be0f  mov     rdi, rdx
0x18000be12  call    cs:__imp_CoTaskMemAlloc
0x18000be18  mov     r8, rax
0x18000be1b  test    rax, rax
0x18000be1e  jnz     short loc_18000BE27
0x18000be20  mov     eax, 8007000Eh
0x18000be25  jmp     short loc_18000BE4F
0x18000be27  movups  xmm0, xmmword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data1
0x18000be2e  lea     rdx, [rsp+28h+arg_8]
0x18000be33  mov     [rsp+28h+arg_8], 1
0x18000be3b  movdqu  xmmword ptr [rax], xmm0
0x18000be3f  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$00U?$ImplementsMarker@U?$Implements@VFtmBase@WRL@Microsoft@@UIProcessLauncherStatics@System@Windows@@@WRL@Microsoft@@@Details@23@UIInspectable@@VNil@523@V7523@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::System::IProcessLauncherStatics>>,IInspectable,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::FillArrayWithIid(ulong *,_GUID *)
0x18000be44  mov     dword ptr [rdi], 3
0x18000be4a  xor     eax, eax
0x18000be4c  mov     [rbx], r8
0x18000be4f  mov     rbx, [rsp+28h+arg_0]
0x18000be54  add     rsp, 20h
0x18000be58  pop     rdi
0x18000be59  retn
```
