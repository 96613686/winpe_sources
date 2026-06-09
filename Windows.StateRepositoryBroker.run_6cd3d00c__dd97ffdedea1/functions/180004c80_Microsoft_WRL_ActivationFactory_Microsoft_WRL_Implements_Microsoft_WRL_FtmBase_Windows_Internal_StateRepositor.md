# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::StateRepository::IApplicationResourceResolverStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetIids(ulong *,_GUID * *)

- ea: `0x180004c80`
- end: `0x180004cdf`
- name: `?GetIids@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIApplicationResourceResolverStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004cf0`

## callees

- `0x1800047a8`
- `0x180004c80`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004ca2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004ca2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::StateRepository::IApplicationResourceResolverStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetIids(
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
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::StateRepository::IApplicationResourceResolverStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::FillArrayWithIid(
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
0x180004c80  mov     [rsp+arg_0], rbx
0x180004c85  push    rdi
0x180004c86  sub     rsp, 20h
0x180004c8a  mov     qword ptr [r8], 0
0x180004c91  mov     ecx, 20h ; ' '; cb
0x180004c96  mov     dword ptr [rdx], 0
0x180004c9c  mov     rbx, r8
0x180004c9f  mov     rdi, rdx
0x180004ca2  call    cs:__imp_CoTaskMemAlloc
0x180004ca8  mov     r8, rax
0x180004cab  test    rax, rax
0x180004cae  jnz     short loc_180004CB7
0x180004cb0  mov     eax, 8007000Eh
0x180004cb5  jmp     short loc_180004CD4
0x180004cb7  lea     rdx, [rsp+28h+arg_8]
0x180004cbc  mov     [rsp+28h+arg_8], 0
0x180004cc4  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@UIActivationFactory@@U?$Implements@VFtmBase@WRL@Microsoft@@UIApplicationResourceResolverStatics@StateRepository@Internal@Windows@@@23@VNil@Details@23@V6723@V6723@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::StateRepository::IApplicationResourceResolverStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::FillArrayWithIid(ulong *,_GUID *)
0x180004cc9  mov     dword ptr [rdi], 2
0x180004ccf  xor     eax, eax
0x180004cd1  mov     [rbx], r8
0x180004cd4  mov     rbx, [rsp+28h+arg_0]
0x180004cd9  add     rsp, 20h
0x180004cdd  pop     rdi
0x180004cde  retn
```
