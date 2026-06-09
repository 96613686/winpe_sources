# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetIids(ulong *,_GUID * *)

- ea: `0x18001a450`
- end: `0x18001a4af`
- name: `?GetIids@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001a4c0`

## callees

- `0x18001a420`
- `0x18001a450`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a472`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a472`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetIids(
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
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::FillArrayWithIid(
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
0x18001a450  mov     [rsp+arg_0], rbx
0x18001a455  push    rdi
0x18001a456  sub     rsp, 20h
0x18001a45a  mov     qword ptr [r8], 0
0x18001a461  mov     ecx, 20h ; ' '; cb
0x18001a466  mov     dword ptr [rdx], 0
0x18001a46c  mov     rbx, r8
0x18001a46f  mov     rdi, rdx
0x18001a472  call    cs:__imp_CoTaskMemAlloc
0x18001a478  mov     r8, rax
0x18001a47b  test    rax, rax
0x18001a47e  jnz     short loc_18001A487
0x18001a480  mov     eax, 8007000Eh
0x18001a485  jmp     short loc_18001A4A4
0x18001a487  lea     rdx, [rsp+28h+arg_8]
0x18001a48c  mov     [rsp+28h+arg_8], 0
0x18001a494  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@UIActivationFactory@@U?$Implements@VFtmBase@WRL@Microsoft@@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@23@VNil@Details@23@V6723@V6723@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::FillArrayWithIid(ulong *,_GUID *)
0x18001a499  mov     dword ptr [rdi], 2
0x18001a49f  xor     eax, eax
0x18001a4a1  mov     [rbx], r8
0x18001a4a4  mov     rbx, [rsp+28h+arg_0]
0x18001a4a9  add     rsp, 20h
0x18001a4ad  pop     rdi
0x18001a4ae  retn
```
