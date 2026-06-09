# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Storage::IApplicationDataStatics>,Windows::Storage::IApplicationDataStatics2,Microsoft::WRL::Details::Nil,0>::GetIids(ulong *,_GUID * *)

- ea: `0x180027a20`
- end: `0x180027a8a`
- name: `?GetIids@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIApplicationDataStatics@Storage@Windows@@@WRL@Microsoft@@UIApplicationDataStatics2@Storage@Windows@@VNil@Details@23@$0A@@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `106`
- prototype: `HRESULT __fastcall(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<13>,0,1,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Storage::IApplicationDataStatics>,Windows::Storage::IApplicationDataStatics2,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil> *this, unsigned int *iidCount, _GUID **iids)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180027a90`
- `0x180027aa0`

## callees

- `0x18002769c`
- `0x180027a20`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027a42`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027a42`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Storage::IApplicationDataStatics>,Windows::Storage::IApplicationDataStatics2,Microsoft::WRL::Details::Nil,0>::GetIids(
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<13>,0,1,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Storage::IApplicationDataStatics>,Windows::Storage::IApplicationDataStatics2,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil> *this,
        unsigned int *iidCount,
        _GUID **iids)
{
  _GUID *v5; // rax
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Storage::IApplicationDataStatics> >,Windows::Storage::IApplicationDataStatics2,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil> *v6; // rcx
  __int64 result; // rax
  _GUID *v8; // r8
  unsigned int index; // [rsp+38h] [rbp+10h] BYREF

  *iids = 0;
  *iidCount = 0;
  v5 = (_GUID *)CoTaskMemAlloc(0x30u);
  if ( !v5 )
    return 2147942414LL;
  index = 1;
  *v5 = GUID_00000035_0000_0000_c000_000000000046;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Storage::IApplicationDataStatics>>,Windows::Storage::IApplicationDataStatics2,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::FillArrayWithIid(
    v6,
    &index,
    v5);
  *iidCount = 3;
  result = 0;
  *iids = v8;
  return result;
}

```

## disassembly

```asm
0x180027a20  mov     [rsp+arg_0], rbx
0x180027a25  push    rdi
0x180027a26  sub     rsp, 20h
0x180027a2a  mov     qword ptr [iids], 0
0x180027a31  mov     ecx, 30h ; '0'; cb
0x180027a36  mov     dword ptr [iidCount], 0
0x180027a3c  mov     rbx, iids
0x180027a3f  mov     rdi, iidCount
0x180027a42  call    cs:__imp_CoTaskMemAlloc
0x180027a48  mov     iids, rax; iids
0x180027a4b  test    rax, rax
0x180027a4e  jnz     short loc_180027A57
0x180027a50  mov     eax, 8007000Eh
0x180027a55  jmp     short loc_180027A7F
0x180027a57  movups  xmm0, xmmword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data1
0x180027a5e  lea     iidCount, [rsp+28h+index]; index
0x180027a63  mov     [rsp+28h+index], 1
0x180027a6b  movdqu  xmmword ptr [rax], xmm0
0x180027a6f  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$00U?$ImplementsMarker@U?$Implements@VFtmBase@WRL@Microsoft@@UIApplicationDataStatics@Storage@Windows@@@WRL@Microsoft@@@Details@23@UIApplicationDataStatics2@Storage@Windows@@VNil@523@V9523@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Storage::IApplicationDataStatics>>,Windows::Storage::IApplicationDataStatics2,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::FillArrayWithIid(ulong *,_GUID *)
0x180027a74  mov     dword ptr [rdi], 3
0x180027a7a  xor     eax, eax
0x180027a7c  mov     [rbx], iids
0x180027a7f  mov     rbx, [rsp+28h+arg_0]
0x180027a84  add     rsp, 20h
0x180027a88  pop     rdi
0x180027a89  retn
```
