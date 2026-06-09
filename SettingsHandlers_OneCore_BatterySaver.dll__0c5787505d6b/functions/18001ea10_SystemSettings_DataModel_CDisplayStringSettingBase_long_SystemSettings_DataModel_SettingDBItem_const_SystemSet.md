# SystemSettings::DataModel::CDisplayStringSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::GetIids(ulong *,_GUID * *)

- ea: `0x18001ea10`
- end: `0x18001ea92`
- name: `?GetIids@?$CDisplayStringSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `130`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001eaa0`
- `0x18001eab0`
- `0x18001eac0`

## callees

- `0x18001da50`
- `0x18001ea10`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ea32`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ea32`

## pseudocode

```c
__int64 __fastcall SystemSettings::DataModel::CDisplayStringSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::GetIids(
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
  v5 = (GUID *)CoTaskMemAlloc(0x50u);
  if ( !v5 )
    return 2147942414LL;
  v9 = 3;
  *v5 = GUID_40c037cc_d8bf_489e_8697_d66baa3221bf;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  v5[2] = GUID_7cf1e617_fe1e_48ef_8962_40a425d21d7e;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    v6,
    &v9,
    v5);
  *a2 = 5;
  result = 0;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x18001ea10  mov     [rsp+arg_0], rbx
0x18001ea15  push    rdi
0x18001ea16  sub     rsp, 20h
0x18001ea1a  mov     qword ptr [r8], 0
0x18001ea21  mov     ecx, 50h ; 'P'; cb
0x18001ea26  mov     dword ptr [rdx], 0
0x18001ea2c  mov     rbx, r8
0x18001ea2f  mov     rdi, rdx
0x18001ea32  call    cs:__imp_CoTaskMemAlloc
0x18001ea38  mov     r8, rax
0x18001ea3b  test    rax, rax
0x18001ea3e  jnz     short loc_18001EA47
0x18001ea40  mov     eax, 8007000Eh
0x18001ea45  jmp     short loc_18001EA87
0x18001ea47  movups  xmm0, xmmword ptr cs:_GUID_40c037cc_d8bf_489e_8697_d66baa3221bf.Data1
0x18001ea4e  lea     rdx, [rsp+28h+arg_8]
0x18001ea53  mov     [rsp+28h+arg_8], 3
0x18001ea5b  movdqu  xmmword ptr [rax], xmm0
0x18001ea5f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x18001ea66  movdqu  xmmword ptr [rax+10h], xmm1
0x18001ea6b  movups  xmm0, xmmword ptr cs:_GUID_7cf1e617_fe1e_48ef_8962_40a425d21d7e.Data1
0x18001ea72  movdqu  xmmword ptr [rax+20h], xmm0
0x18001ea77  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UISettingsAppNotification@DataModel@SystemSettings@@UISettingItem2@56@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x18001ea7c  mov     dword ptr [rdi], 5
0x18001ea82  xor     eax, eax
0x18001ea84  mov     [rbx], r8
0x18001ea87  mov     rbx, [rsp+28h+arg_0]
0x18001ea8c  add     rsp, 20h
0x18001ea90  pop     rdi
0x18001ea91  retn
```
