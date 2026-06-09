# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<13>,0,1,0,IActivationFactory,Windows::Security::Authentication::Web::IWebAuthenticationBrokerStatics,Windows::Security::Authentication::Web::IWebAuthenticationBrokerStatics2,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::GetIids(ulong *,_GUID * *)

- ea: `0x18000b3c0`
- end: `0x18000b42d`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@$00$0A@UIActivationFactory@@UIWebAuthenticationBrokerStatics@Web@Authentication@Security@Windows@@UIWebAuthenticationBrokerStatics2@6789@VNil@Details@23@VNil@Details@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `109`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<13>,0,1,0,IActivationFactory,Windows::Security::Authentication::Web::IWebAuthenticationBrokerStatics,Windows::Security::Authentication::Web::IWebAuthenticationBrokerStatics2,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil> *this, unsigned int *iidCount, _GUID **iids)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b440`
- `0x18000b450`

## callees

- `0x18000b3c0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b3e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b3e2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<13>,0,1,0,IActivationFactory,Windows::Security::Authentication::Web::IWebAuthenticationBrokerStatics,Windows::Security::Authentication::Web::IWebAuthenticationBrokerStatics2,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::GetIids(
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<13>,0,1,0,IActivationFactory,Windows::Security::Authentication::Web::IWebAuthenticationBrokerStatics,Windows::Security::Authentication::Web::IWebAuthenticationBrokerStatics2,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil> *this,
        unsigned int *iidCount,
        _GUID **iids)
{
  _GUID *v5; // rax

  *iids = 0;
  *iidCount = 0;
  v5 = (_GUID *)CoTaskMemAlloc(0x30u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_00000035_0000_0000_c000_000000000046;
  v5[1] = GUID_2f149f1a_e673_40b5_bc22_201a6864a37b;
  v5[2] = GUID_73cdfb9e_14e7_41da_a971_aaf4410b621e;
  *iidCount = 3;
  *iids = v5;
  return 0;
}

```

## disassembly

```asm
0x18000b3c0  mov     [rsp+arg_0], rbx
0x18000b3c5  push    rdi
0x18000b3c6  sub     rsp, 20h
0x18000b3ca  mov     qword ptr [iids], 0
0x18000b3d1  mov     ecx, 30h ; '0'; cb
0x18000b3d6  mov     dword ptr [iidCount], 0
0x18000b3dc  mov     rbx, iids
0x18000b3df  mov     rdi, iidCount
0x18000b3e2  call    cs:__imp_CoTaskMemAlloc
0x18000b3e8  test    rax, rax
0x18000b3eb  jnz     short loc_18000B3F4
0x18000b3ed  mov     eax, 8007000Eh
0x18000b3f2  jmp     short loc_18000B422
0x18000b3f4  movups  xmm0, xmmword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data1
0x18000b3fb  movdqu  xmmword ptr [rax], xmm0
0x18000b3ff  movups  xmm1, xmmword ptr cs:_GUID_2f149f1a_e673_40b5_bc22_201a6864a37b.Data1
0x18000b406  movdqu  xmmword ptr [rax+10h], xmm1
0x18000b40b  movups  xmm0, xmmword ptr cs:_GUID_73cdfb9e_14e7_41da_a971_aaf4410b621e.Data1
0x18000b412  movdqu  xmmword ptr [rax+20h], xmm0
0x18000b417  mov     dword ptr [rdi], 3
0x18000b41d  mov     [rbx], rax
0x18000b420  xor     eax, eax
0x18000b422  mov     rbx, [rsp+28h+arg_0]
0x18000b427  add     rsp, 20h
0x18000b42b  pop     rdi
0x18000b42c  retn
```
