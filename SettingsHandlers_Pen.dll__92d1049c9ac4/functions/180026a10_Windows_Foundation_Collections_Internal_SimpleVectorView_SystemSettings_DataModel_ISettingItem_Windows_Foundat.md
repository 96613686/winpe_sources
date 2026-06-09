# Windows::Foundation::Collections::Internal::SimpleVectorView<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,XWinRT::IntVersionTag,1>::GetIids(ulong *,_GUID * *)

- ea: `0x180026a10`
- end: `0x180026a7d`
- name: `?GetIids@?$SimpleVectorView@PEAUISettingItem@DataModel@SystemSettings@@V?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@UIntVersionTag@XWinRT@@$00@Internal@Collections@Foundation@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `109`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180026a90`

## callees

- `0x180026a10`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180026a32`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180026a32`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::SimpleVectorView<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,XWinRT::IntVersionTag,1>::GetIids(
        __int64 a1,
        _DWORD *a2,
        GUID **a3)
{
  GUID *v5; // rax

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x30u);
  if ( !v5 )
    return 2147942414LL;
  *v5 = GUID_2748819e_b5b7_5f54_a337_c04593b19e74;
  v5[1] = GUID_00000038_0000_0000_c000_000000000046;
  v5[2] = GUID_2aab4305_70a6_58fc_8050_199102b52440;
  *a2 = 3;
  *a3 = v5;
  return 0;
}

```

## disassembly

```asm
0x180026a10  mov     [rsp+arg_0], rbx
0x180026a15  push    rdi
0x180026a16  sub     rsp, 20h
0x180026a1a  mov     qword ptr [r8], 0
0x180026a21  mov     ecx, 30h ; '0'; cb
0x180026a26  mov     dword ptr [rdx], 0
0x180026a2c  mov     rbx, r8
0x180026a2f  mov     rdi, rdx
0x180026a32  call    cs:__imp_CoTaskMemAlloc
0x180026a38  test    rax, rax
0x180026a3b  jnz     short loc_180026A44
0x180026a3d  mov     eax, 8007000Eh
0x180026a42  jmp     short loc_180026A72
0x180026a44  movups  xmm0, xmmword ptr cs:_GUID_2748819e_b5b7_5f54_a337_c04593b19e74.Data1
0x180026a4b  movdqu  xmmword ptr [rax], xmm0
0x180026a4f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180026a56  movdqu  xmmword ptr [rax+10h], xmm1
0x180026a5b  movups  xmm0, xmmword ptr cs:_GUID_2aab4305_70a6_58fc_8050_199102b52440.Data1
0x180026a62  movdqu  xmmword ptr [rax+20h], xmm0
0x180026a67  mov     dword ptr [rdi], 3
0x180026a6d  mov     [rbx], rax
0x180026a70  xor     eax, eax
0x180026a72  mov     rbx, [rsp+28h+arg_0]
0x180026a77  add     rsp, 20h
0x180026a7b  pop     rdi
0x180026a7c  retn
```
