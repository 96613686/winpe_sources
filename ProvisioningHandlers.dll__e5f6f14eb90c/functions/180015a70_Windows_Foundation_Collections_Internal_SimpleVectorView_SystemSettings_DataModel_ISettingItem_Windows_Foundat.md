# Windows::Foundation::Collections::Internal::SimpleVectorView<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,XWinRT::IntVersionTag,1>::GetIids(ulong *,_GUID * *)

- ea: `0x180015a70`
- end: `0x180015ae1`
- name: `?GetIids@?$SimpleVectorView@PEAUISettingItem@DataModel@SystemSettings@@V?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@UIntVersionTag@XWinRT@@$00@Internal@Collections@Foundation@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `113`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180015af0`

## callees

- `0x180014a84`
- `0x180015a70`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015a92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015a92`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::SimpleVectorView<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,XWinRT::IntVersionTag,1>::GetIids(
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
  v5 = (GUID *)CoTaskMemAlloc(0x30u);
  if ( !v5 )
    return 2147942414LL;
  v9 = 1;
  *v5 = GUID_2748819e_b5b7_5f54_a337_c04593b19e74;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<SystemSettings::DataModel::ISettingItem *>,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    v6,
    &v9,
    v5);
  *a2 = 3;
  result = 0;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x180015a70  mov     [rsp+arg_0], rbx
0x180015a75  push    rdi
0x180015a76  sub     rsp, 20h
0x180015a7a  mov     qword ptr [r8], 0
0x180015a81  mov     ecx, 30h ; '0'; cb
0x180015a86  mov     dword ptr [rdx], 0
0x180015a8c  mov     rbx, r8
0x180015a8f  mov     rdi, rdx
0x180015a92  call    cs:__imp_CoTaskMemAlloc
0x180015a99  nop     dword ptr [rax+rax+00h]
0x180015a9e  mov     r8, rax
0x180015aa1  test    rax, rax
0x180015aa4  jnz     short loc_180015AAD
0x180015aa6  mov     eax, 8007000Eh
0x180015aab  jmp     short loc_180015AD5
0x180015aad  movups  xmm0, xmmword ptr cs:_GUID_2748819e_b5b7_5f54_a337_c04593b19e74.Data1
0x180015ab4  lea     rdx, [rsp+28h+arg_8]
0x180015ab9  mov     [rsp+28h+arg_8], 1
0x180015ac1  movdqu  xmmword ptr [rax], xmm0
0x180015ac5  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@U?$IIterable@PEAUISettingItem@DataModel@SystemSettings@@@Collections@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<SystemSettings::DataModel::ISettingItem *>,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x180015aca  mov     dword ptr [rdi], 3
0x180015ad0  xor     eax, eax
0x180015ad2  mov     [rbx], r8
0x180015ad5  mov     rbx, [rsp+28h+arg_0]
0x180015ada  add     rsp, 20h
0x180015ade  pop     rdi
0x180015adf  retn
```
