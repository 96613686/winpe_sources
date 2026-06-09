# Microsoft::Bluetooth::Profiles::MediaControl::Interface::MediaControlOperationHandler::GetIids(ulong *,_GUID * *)

- ea: `0x18002da30`
- end: `0x18002da9a`
- name: `?GetIids@MediaControlOperationHandler@Interface@MediaControl@Profiles@Bluetooth@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `106`
- prototype: `__int64 __fastcall(Microsoft::Bluetooth::Profiles::MediaControl::Interface::MediaControlOperationHandler *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18002d774`
- `0x18002da30`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002da52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002da52`

## pseudocode

```c
__int64 __fastcall Microsoft::Bluetooth::Profiles::MediaControl::Interface::MediaControlOperationHandler::GetIids(
        Microsoft::Bluetooth::Profiles::MediaControl::Interface::MediaControlOperationHandler *this,
        unsigned int *a2,
        struct _GUID **a3)
{
  GUID *v5; // rax
  __int64 v6; // rcx
  __int64 result; // rax
  struct _GUID *v8; // r8
  int v9; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x30u);
  if ( !v5 )
    return 2147942414LL;
  v9 = 1;
  *v5 = GUID_d5294822_630a_547d_b583_94cd8c6eed7b;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,IBthAvMediaEventHandler,Microsoft::WRL::FtmBase>::FillArrayWithIid(
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
0x18002da30  mov     [rsp+arg_0], rbx
0x18002da35  push    rdi
0x18002da36  sub     rsp, 20h
0x18002da3a  mov     qword ptr [r8], 0
0x18002da41  mov     ecx, 30h ; '0'; cb
0x18002da46  mov     dword ptr [rdx], 0
0x18002da4c  mov     rbx, r8
0x18002da4f  mov     rdi, rdx
0x18002da52  call    cs:__imp_CoTaskMemAlloc
0x18002da58  mov     r8, rax
0x18002da5b  test    rax, rax
0x18002da5e  jnz     short loc_18002DA67
0x18002da60  mov     eax, 8007000Eh
0x18002da65  jmp     short loc_18002DA8F
0x18002da67  movups  xmm0, xmmword ptr cs:_GUID_d5294822_630a_547d_b583_94cd8c6eed7b.Data1
0x18002da6e  lea     rdx, [rsp+28h+arg_8]
0x18002da73  mov     [rsp+28h+arg_8], 1
0x18002da7b  movdqu  xmmword ptr [rax], xmm0
0x18002da7f  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@UIBthAvMediaEventHandler@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,IBthAvMediaEventHandler,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x18002da84  mov     dword ptr [rdi], 3
0x18002da8a  xor     eax, eax
0x18002da8c  mov     [rbx], r8
0x18002da8f  mov     rbx, [rsp+28h+arg_0]
0x18002da94  add     rsp, 20h
0x18002da98  pop     rdi
0x18002da99  retn
```
