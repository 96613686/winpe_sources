# SystemSettings::DataModel::CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::GetIids(ulong *,_GUID * *)

- ea: `0x18000edf0`
- end: `0x18000ee72`
- name: `?GetIids@?$CDataSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `130`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000ee80`
- `0x18000ee90`
- `0x18000eea0`

## callees

- `0x18000eb1c`
- `0x18000edf0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ee12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ee12`

## pseudocode

```c
__int64 __fastcall SystemSettings::DataModel::CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::GetIids(
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
0x18000edf0  mov     [rsp+arg_0], rbx
0x18000edf5  push    rdi
0x18000edf6  sub     rsp, 20h
0x18000edfa  mov     qword ptr [r8], 0
0x18000ee01  mov     ecx, 50h ; 'P'; cb
0x18000ee06  mov     dword ptr [rdx], 0
0x18000ee0c  mov     rbx, r8
0x18000ee0f  mov     rdi, rdx
0x18000ee12  call    cs:__imp_CoTaskMemAlloc
0x18000ee18  mov     r8, rax
0x18000ee1b  test    rax, rax
0x18000ee1e  jnz     short loc_18000EE27
0x18000ee20  mov     eax, 8007000Eh
0x18000ee25  jmp     short loc_18000EE67
0x18000ee27  movups  xmm0, xmmword ptr cs:_GUID_40c037cc_d8bf_489e_8697_d66baa3221bf.Data1
0x18000ee2e  lea     rdx, [rsp+28h+arg_8]
0x18000ee33  mov     [rsp+28h+arg_8], 3
0x18000ee3b  movdqu  xmmword ptr [rax], xmm0
0x18000ee3f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x18000ee46  movdqu  xmmword ptr [rax+10h], xmm1
0x18000ee4b  movups  xmm0, xmmword ptr cs:_GUID_7cf1e617_fe1e_48ef_8962_40a425d21d7e.Data1
0x18000ee52  movdqu  xmmword ptr [rax+20h], xmm0
0x18000ee57  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UISettingsAppNotification@DataModel@SystemSettings@@UISettingItem2@56@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x18000ee5c  mov     dword ptr [rdi], 5
0x18000ee62  xor     eax, eax
0x18000ee64  mov     [rbx], r8
0x18000ee67  mov     rbx, [rsp+28h+arg_0]
0x18000ee6c  add     rsp, 20h
0x18000ee70  pop     rdi
0x18000ee71  retn
```
