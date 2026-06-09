# Windows::Storage::ApplicationDataCompositeValueServer::GetIids(ulong *,_GUID * *)

- ea: `0x180034f30`
- end: `0x180034fbe`
- name: `?GetIids@ApplicationDataCompositeValueServer@Storage@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `142`
- prototype: `HRESULT __fastcall(Windows::Storage::ApplicationDataCompositeValueServer *this, unsigned int *iidCount, _GUID **iids)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180034fd0`
- `0x180034fe0`
- `0x180034ff0`
- `0x180035000`

## callees

- `0x180034f00`
- `0x180034f30`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180034f52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180034f52`

## pseudocode

```c
__int64 __fastcall Windows::Storage::ApplicationDataCompositeValueServer::GetIids(
        Windows::Storage::ApplicationDataCompositeValueServer *this,
        unsigned int *iidCount,
        _GUID **iids)
{
  _GUID *v5; // rax
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase> *v6; // rcx
  __int64 result; // rax
  _GUID *v8; // r8
  unsigned int index; // [rsp+38h] [rbp+10h] BYREF

  *iids = 0;
  *iidCount = 0;
  v5 = (_GUID *)CoTaskMemAlloc(0x60u);
  if ( !v5 )
    return 2147942414LL;
  index = 4;
  *v5 = GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  v5[2] = GUID_fe2f3d47_5d47_5499_8374_430c7cda0204;
  v5[3] = GUID_236aac9d_fb12_5c4d_a41c_9e445fb4d7ec;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    v6,
    &index,
    v5);
  *iidCount = 6;
  result = 0;
  *iids = v8;
  return result;
}

```

## disassembly

```asm
0x180034f30  mov     [rsp+arg_0], rbx
0x180034f35  push    rdi
0x180034f36  sub     rsp, 20h
0x180034f3a  mov     qword ptr [iids], 0
0x180034f41  mov     ecx, 60h ; '`'; cb
0x180034f46  mov     dword ptr [iidCount], 0
0x180034f4c  mov     rbx, iids
0x180034f4f  mov     rdi, iidCount
0x180034f52  call    cs:__imp_CoTaskMemAlloc
0x180034f58  mov     iids, rax; iids
0x180034f5b  test    rax, rax
0x180034f5e  jnz     short loc_180034F67
0x180034f60  mov     eax, 8007000Eh
0x180034f65  jmp     short loc_180034FB3
0x180034f67  movups  xmm0, xmmword ptr cs:_GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca.Data1
0x180034f6e  lea     iidCount, [rsp+28h+index]; index
0x180034f73  mov     [rsp+28h+index], 4
0x180034f7b  movdqu  xmmword ptr [rax], xmm0
0x180034f7f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180034f86  movdqu  xmmword ptr [rax+10h], xmm1
0x180034f8b  movups  xmm0, xmmword ptr cs:_GUID_fe2f3d47_5d47_5499_8374_430c7cda0204.Data1
0x180034f92  movdqu  xmmword ptr [rax+20h], xmm0
0x180034f97  movups  xmm1, xmmword ptr cs:_GUID_236aac9d_fb12_5c4d_a41c_9e445fb4d7ec.Data1
0x180034f9e  movdqu  xmmword ptr [rax+30h], xmm1
0x180034fa3  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIPropertySet@Collections@Foundation@Windows@@UIApplicationDataCompositeValueInternal@Private@Storage@7@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x180034fa8  mov     dword ptr [rdi], 6
0x180034fae  xor     eax, eax
0x180034fb0  mov     [rbx], iids
0x180034fb3  mov     rbx, [rsp+28h+arg_0]
0x180034fb8  add     rsp, 20h
0x180034fbc  pop     rdi
0x180034fbd  retn
```
