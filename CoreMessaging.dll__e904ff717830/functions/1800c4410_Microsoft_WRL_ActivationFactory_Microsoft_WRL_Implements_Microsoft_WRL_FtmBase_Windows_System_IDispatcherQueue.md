# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::System::IDispatcherQueueStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetIids(ulong *,_GUID * *)

- ea: `0x1800c4410`
- end: `0x1800c446f`
- name: `?GetIids@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIDispatcherQueueStatics@System@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800c4480`

## callees

- `0x1800c426c`
- `0x1800c4410`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c4432`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c4432`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::System::IDispatcherQueueStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetIids(
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
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::System::IDispatcherQueueStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::FillArrayWithIid(
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
0x1800c4410  mov     [rsp+arg_0], rbx
0x1800c4415  push    rdi
0x1800c4416  sub     rsp, 20h
0x1800c441a  mov     qword ptr [r8], 0
0x1800c4421  mov     ecx, 20h ; ' '; cb
0x1800c4426  mov     dword ptr [rdx], 0
0x1800c442c  mov     rbx, r8
0x1800c442f  mov     rdi, rdx
0x1800c4432  call    cs:__imp_CoTaskMemAlloc
0x1800c4438  mov     r8, rax
0x1800c443b  test    rax, rax
0x1800c443e  jnz     short loc_1800C4447
0x1800c4440  mov     eax, 8007000Eh
0x1800c4445  jmp     short loc_1800C4464
0x1800c4447  lea     rdx, [rsp+28h+arg_8]
0x1800c444c  mov     [rsp+28h+arg_8], 0
0x1800c4454  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@UIActivationFactory@@U?$Implements@VFtmBase@WRL@Microsoft@@UIDispatcherQueueStatics@System@Windows@@@23@VNil@Details@23@V6723@V6723@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::System::IDispatcherQueueStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::FillArrayWithIid(ulong *,_GUID *)
0x1800c4459  mov     dword ptr [rdi], 2
0x1800c445f  xor     eax, eax
0x1800c4461  mov     [rbx], r8
0x1800c4464  mov     rbx, [rsp+28h+arg_0]
0x1800c4469  add     rsp, 20h
0x1800c446d  pop     rdi
0x1800c446e  retn
```
