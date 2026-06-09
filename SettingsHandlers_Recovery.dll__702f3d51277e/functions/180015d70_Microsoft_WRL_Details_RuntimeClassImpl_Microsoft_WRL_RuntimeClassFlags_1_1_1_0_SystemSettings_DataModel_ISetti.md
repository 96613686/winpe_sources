# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,SystemSettings::DataModel::ISettingItem,SystemSettings::DataModel::ISettingItemTelemetry,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x180015d70`
- end: `0x180015df5`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UISettingItem@DataModel@SystemSettings@@UISettingItemTelemetry@56@UISettingsAppNotification@56@UISettingItem2@56@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `133`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180015b30`
- `0x180015e00`
- `0x180015e10`
- `0x180015e20`

## callees

- `0x180015d70`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180015d92`
- `ole32!CoTaskMemAlloc` at `0x180015d92`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,SystemSettings::DataModel::ISettingItem,SystemSettings::DataModel::ISettingItemTelemetry,SystemSettings::DataModel::ISettingsAppNotification,SystemSettings::DataModel::ISettingItem2,Microsoft::WRL::FtmBase>::GetIids(
        __int64 a1,
        _DWORD *a2,
        GUID **a3)
{
  GUID *v5; // rax

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x50u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_40c037cc_d8bf_489e_8697_d66baa3221bf;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  v5[2] = GUID_7cf1e617_fe1e_48ef_8962_40a425d21d7e;
  v5[3] = GUID_dff43ddc_7d1d_4899_94c5_a2a06e177712;
  v5[4] = GUID_32572999_399d_40ff_a423_3595b4dc993b;
  *a2 = 5;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180015d70  mov     [rsp+arg_0], rbx
0x180015d75  push    rdi
0x180015d76  sub     rsp, 20h
0x180015d7a  mov     qword ptr [r8], 0
0x180015d81  mov     ecx, 50h ; 'P'; cb
0x180015d86  mov     dword ptr [rdx], 0
0x180015d8c  mov     rbx, r8
0x180015d8f  mov     rdi, rdx
0x180015d92  call    cs:__imp_CoTaskMemAlloc
0x180015d98  test    rax, rax
0x180015d9b  jnz     short loc_180015DA4
0x180015d9d  mov     eax, 8007000Eh
0x180015da2  jmp     short loc_180015DEA
0x180015da4  movups  xmm0, xmmword ptr cs:_GUID_40c037cc_d8bf_489e_8697_d66baa3221bf.Data1
0x180015dab  movdqu  xmmword ptr [rax], xmm0
0x180015daf  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180015db6  movdqu  xmmword ptr [rax+10h], xmm1
0x180015dbb  movups  xmm0, xmmword ptr cs:_GUID_7cf1e617_fe1e_48ef_8962_40a425d21d7e.Data1
0x180015dc2  movdqu  xmmword ptr [rax+20h], xmm0
0x180015dc7  movups  xmm1, xmmword ptr cs:_GUID_dff43ddc_7d1d_4899_94c5_a2a06e177712.Data1
0x180015dce  movdqu  xmmword ptr [rax+30h], xmm1
0x180015dd3  movups  xmm0, xmmword ptr cs:_GUID_32572999_399d_40ff_a423_3595b4dc993b.Data1
0x180015dda  movdqu  xmmword ptr [rax+40h], xmm0
0x180015ddf  mov     dword ptr [rdi], 5
0x180015de5  mov     [rbx], rax
0x180015de8  xor     eax, eax
0x180015dea  mov     rbx, [rsp+28h+arg_0]
0x180015def  add     rsp, 20h
0x180015df3  pop     rdi
0x180015df4  retn
```
