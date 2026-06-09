# SystemSettings::DataModel::CDisplayStringSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::GetIids(ulong *,_GUID * *)

- ea: `0x180012340`
- end: `0x1800123c9`
- name: `?GetIids@?$CDisplayStringSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `137`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800123d0`
- `0x1800123e0`
- `0x1800123f0`

## callees

- `0x180011d78`
- `0x180012340`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012362`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012362`

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
0x180012340  mov     [rsp+arg_0], rbx
0x180012345  push    rdi
0x180012346  sub     rsp, 20h
0x18001234a  mov     qword ptr [r8], 0
0x180012351  mov     ecx, 50h ; 'P'; cb
0x180012356  mov     dword ptr [rdx], 0
0x18001235c  mov     rbx, r8
0x18001235f  mov     rdi, rdx
0x180012362  call    cs:__imp_CoTaskMemAlloc
0x180012369  nop     dword ptr [rax+rax+00h]
0x18001236e  mov     r8, rax
0x180012371  test    rax, rax
0x180012374  jnz     short loc_18001237D
0x180012376  mov     eax, 8007000Eh
0x18001237b  jmp     short loc_1800123BD
0x18001237d  movups  xmm0, xmmword ptr cs:_GUID_40c037cc_d8bf_489e_8697_d66baa3221bf.Data1
0x180012384  lea     rdx, [rsp+28h+arg_8]
0x180012389  mov     [rsp+28h+arg_8], 3
0x180012391  movdqu  xmmword ptr [rax], xmm0
0x180012395  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x18001239c  movdqu  xmmword ptr [rax+10h], xmm1
0x1800123a1  movups  xmm0, xmmword ptr cs:_GUID_7cf1e617_fe1e_48ef_8962_40a425d21d7e.Data1
0x1800123a8  movdqu  xmmword ptr [rax+20h], xmm0
0x1800123ad  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UISettingsAppNotification@DataModel@SystemSettings@@UISettingItem2@56@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x1800123b2  mov     dword ptr [rdi], 5
0x1800123b8  xor     eax, eax
0x1800123ba  mov     [rbx], r8
0x1800123bd  mov     rbx, [rsp+28h+arg_0]
0x1800123c2  add     rsp, 20h
0x1800123c6  pop     rdi
0x1800123c7  retn
```
