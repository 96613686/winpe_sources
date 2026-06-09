# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Microsoft::WRL::Implements<Windows::Networking::UX::IMbConnectionProfileFactory,>>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetIids(ulong *,_GUID * *)

- ea: `0x1800319b0`
- end: `0x180031a0f`
- name: `?GetIids@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@U?$Implements@UIMbConnectionProfileFactory@UX@Networking@Windows@@$$V@23@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180031a20`

## callees

- `0x18003198c`
- `0x1800319b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800319d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800319d2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Microsoft::WRL::Implements<Windows::Networking::UX::IMbConnectionProfileFactory,>>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetIids(
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
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Microsoft::WRL::Implements<Windows::Networking::UX::IMbConnectionProfileFactory,>>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::FillArrayWithIid(
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
0x1800319b0  mov     [rsp+arg_0], rbx
0x1800319b5  push    rdi
0x1800319b6  sub     rsp, 20h
0x1800319ba  mov     qword ptr [r8], 0
0x1800319c1  mov     ecx, 20h ; ' '; cb
0x1800319c6  mov     dword ptr [rdx], 0
0x1800319cc  mov     rbx, r8
0x1800319cf  mov     rdi, rdx
0x1800319d2  call    cs:__imp_CoTaskMemAlloc
0x1800319d8  mov     r8, rax
0x1800319db  test    rax, rax
0x1800319de  jnz     short loc_1800319E7
0x1800319e0  mov     eax, 8007000Eh
0x1800319e5  jmp     short loc_180031A04
0x1800319e7  lea     rdx, [rsp+28h+arg_8]
0x1800319ec  mov     [rsp+28h+arg_8], 0
0x1800319f4  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@UIActivationFactory@@U?$Implements@VFtmBase@WRL@Microsoft@@U?$Implements@UIMbConnectionProfileFactory@UX@Networking@Windows@@$$V@23@@23@VNil@Details@23@V6723@V6723@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Microsoft::WRL::Implements<Windows::Networking::UX::IMbConnectionProfileFactory,>>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::FillArrayWithIid(ulong *,_GUID *)
0x1800319f9  mov     dword ptr [rdi], 2
0x1800319ff  xor     eax, eax
0x180031a01  mov     [rbx], r8
0x180031a04  mov     rbx, [rsp+28h+arg_0]
0x180031a09  add     rsp, 20h
0x180031a0d  pop     rdi
0x180031a0e  retn
```
