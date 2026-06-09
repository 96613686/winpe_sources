# Microsoft::WRL::Details::RuntimeClassBaseT<13>::GetImplementedIIDS<Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::System::ITimeZoneSettingsStatics>,Windows::System::ITimeZoneSettingsStatics2,IInspectable,0>>(Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::System::ITimeZoneSettingsStatics>,Windows::System::ITimeZoneSettingsStatics2,IInspectable,0> *,ulong *,_GUID * *)

- ea: `0x18000a27c`
- end: `0x18000a314`
- name: `??$GetImplementedIIDS@V?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UITimeZoneSettingsStatics@System@Windows@@@WRL@Microsoft@@UITimeZoneSettingsStatics2@System@Windows@@UIInspectable@@$0A@@WRL@Microsoft@@@?$RuntimeClassBaseT@$0N@@Details@WRL@Microsoft@@KAJPEAV?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UITimeZoneSettingsStatics@System@Windows@@@WRL@Microsoft@@UITimeZoneSettingsStatics2@System@Windows@@UIInspectable@@$0A@@23@PEAKPEAPEAU_GUID@@@Z`
- size: `152`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000bec0`

## callees

- `0x18000a27c`
- `0x18000bb24`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a2a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a2a3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassBaseT<13>::GetImplementedIIDS<Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::System::ITimeZoneSettingsStatics>,Windows::System::ITimeZoneSettingsStatics2,IInspectable,0>>(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  GUID *v5; // rax
  __int64 v6; // rcx
  __int64 result; // rax
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // [rsp+30h] [rbp+8h] BYREF

  v10 = a1;
  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x40u);
  if ( !v5 )
    return 2147942414LL;
  LODWORD(v10) = 1;
  *v5 = GUID_00000035_0000_0000_c000_000000000046;
  Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::System::ITimeZoneSettingsStatics>::FillArrayWithIid(
    v6,
    &v10,
    v5);
  v8 = 2LL * (unsigned int)(v10 + 1);
  *(GUID *)(v9 + 16LL * (unsigned int)v10) = GUID_555c0db8_39a8_49fa_b4f6_a2c7fc2842ec;
  result = 0;
  *(GUID *)(v9 + 8 * v8) = GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90;
  *a2 = 4;
  *a3 = v9;
  return result;
}

```

## disassembly

```asm
0x18000a27c  mov     [rsp+arg_8], rbx
0x18000a281  mov     [rsp+arg_0], rcx
0x18000a286  push    rdi
0x18000a287  sub     rsp, 20h
0x18000a28b  mov     qword ptr [r8], 0
0x18000a292  mov     ecx, 40h ; '@'; cb
0x18000a297  mov     dword ptr [rdx], 0
0x18000a29d  mov     rbx, r8
0x18000a2a0  mov     rdi, rdx
0x18000a2a3  call    cs:__imp_CoTaskMemAlloc
0x18000a2a9  mov     r8, rax
0x18000a2ac  test    rax, rax
0x18000a2af  jnz     short loc_18000A2B8
0x18000a2b1  mov     eax, 8007000Eh
0x18000a2b6  jmp     short loc_18000A309
0x18000a2b8  movups  xmm0, xmmword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data1
0x18000a2bf  lea     rdx, [rsp+28h+arg_0]
0x18000a2c4  mov     dword ptr [rsp+28h+arg_0], 1
0x18000a2cc  movdqu  xmmword ptr [rax], xmm0
0x18000a2d0  call    ?FillArrayWithIid@?$Implements@VFtmBase@WRL@Microsoft@@UITimeZoneSettingsStatics@System@Windows@@@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::System::ITimeZoneSettingsStatics>::FillArrayWithIid(ulong *,_GUID *)
0x18000a2d5  movups  xmm0, xmmword ptr cs:_GUID_555c0db8_39a8_49fa_b4f6_a2c7fc2842ec.Data1
0x18000a2dc  mov     edx, dword ptr [rsp+28h+arg_0]
0x18000a2e0  mov     eax, edx
0x18000a2e2  add     rax, rax
0x18000a2e5  lea     ecx, [rdx+1]
0x18000a2e8  add     rcx, rcx
0x18000a2eb  movdqu  xmmword ptr [r8+rax*8], xmm0
0x18000a2f1  xor     eax, eax
0x18000a2f3  movups  xmm0, xmmword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data1
0x18000a2fa  movdqu  xmmword ptr [r8+rcx*8], xmm0
0x18000a300  mov     dword ptr [rdi], 4
0x18000a306  mov     [rbx], r8
0x18000a309  mov     rbx, [rsp+28h+arg_8]
0x18000a30e  add     rsp, 20h
0x18000a312  pop     rdi
0x18000a313  retn
```
