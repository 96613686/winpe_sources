# Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::GetIids(ulong *,_GUID * *)

- ea: `0x180026aa0`
- end: `0x180026b19`
- name: `?GetIids@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180026b20`
- `0x180026b30`

## callees

- `0x180026aa0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180026ac2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180026ac2`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::GetIids(
        __int64 a1,
        _DWORD *a2,
        GUID **a3)
{
  GUID *v5; // rax

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x40u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_ca56de18_3714_5673_982e_3ea0322179bc;
  v5[1] = GUID_2aab4305_70a6_58fc_8050_199102b52440;
  v5[2] = GUID_c5267a7c_640e_5cfc_a7cc_401ccf426e36;
  v5[3] = GUID_00000038_0000_0000_c000_000000000046;
  *a2 = 4;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180026aa0  mov     [rsp+arg_0], rbx
0x180026aa5  push    rdi
0x180026aa6  sub     rsp, 20h
0x180026aaa  mov     qword ptr [r8], 0
0x180026ab1  mov     ecx, 40h ; '@'; cb
0x180026ab6  mov     dword ptr [rdx], 0
0x180026abc  mov     rbx, r8
0x180026abf  mov     rdi, rdx
0x180026ac2  call    cs:__imp_CoTaskMemAlloc
0x180026ac8  test    rax, rax
0x180026acb  jnz     short loc_180026AD4
0x180026acd  mov     eax, 8007000Eh
0x180026ad2  jmp     short loc_180026B0E
0x180026ad4  movups  xmm0, xmmword ptr cs:_GUID_ca56de18_3714_5673_982e_3ea0322179bc.Data1
0x180026adb  movdqu  xmmword ptr [rax], xmm0
0x180026adf  movups  xmm1, xmmword ptr cs:_GUID_2aab4305_70a6_58fc_8050_199102b52440.Data1
0x180026ae6  movdqu  xmmword ptr [rax+10h], xmm1
0x180026aeb  movups  xmm0, xmmword ptr cs:_GUID_c5267a7c_640e_5cfc_a7cc_401ccf426e36.Data1
0x180026af2  movdqu  xmmword ptr [rax+20h], xmm0
0x180026af7  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180026afe  movdqu  xmmword ptr [rax+30h], xmm1
0x180026b03  mov     dword ptr [rdi], 4
0x180026b09  mov     [rbx], rax
0x180026b0c  xor     eax, eax
0x180026b0e  mov     rbx, [rsp+28h+arg_0]
0x180026b13  add     rsp, 20h
0x180026b17  pop     rdi
0x180026b18  retn
```
