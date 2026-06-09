# Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::GetIids(ulong *,_GUID * *)

- ea: `0x180012570`
- end: `0x1800125f9`
- name: `?GetIids@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `137`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180012600`
- `0x180012610`

## callees

- `0x180011dc0`
- `0x180012570`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012592`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012592`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::GetIids(
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
  v5 = (GUID *)CoTaskMemAlloc(0x40u);
  if ( !v5 )
    return 2147942414LL;
  v9 = 3;
  *v5 = GUID_ca56de18_3714_5673_982e_3ea0322179bc;
  v5[1] = GUID_2aab4305_70a6_58fc_8050_199102b52440;
  v5[2] = GUID_c5267a7c_640e_5cfc_a7cc_401ccf426e36;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    v6,
    &v9,
    v5);
  *a2 = 4;
  result = 0;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x180012570  mov     [rsp+arg_0], rbx
0x180012575  push    rdi
0x180012576  sub     rsp, 20h
0x18001257a  mov     qword ptr [r8], 0
0x180012581  mov     ecx, 40h ; '@'; cb
0x180012586  mov     dword ptr [rdx], 0
0x18001258c  mov     rbx, r8
0x18001258f  mov     rdi, rdx
0x180012592  call    cs:__imp_CoTaskMemAlloc
0x180012599  nop     dword ptr [rax+rax+00h]
0x18001259e  mov     r8, rax
0x1800125a1  test    rax, rax
0x1800125a4  jnz     short loc_1800125AD
0x1800125a6  mov     eax, 8007000Eh
0x1800125ab  jmp     short loc_1800125ED
0x1800125ad  movups  xmm0, xmmword ptr cs:_GUID_ca56de18_3714_5673_982e_3ea0322179bc.Data1
0x1800125b4  lea     rdx, [rsp+28h+arg_8]
0x1800125b9  mov     [rsp+28h+arg_8], 3
0x1800125c1  movdqu  xmmword ptr [rax], xmm0
0x1800125c5  movups  xmm1, xmmword ptr cs:_GUID_2aab4305_70a6_58fc_8050_199102b52440.Data1
0x1800125cc  movdqu  xmmword ptr [rax+10h], xmm1
0x1800125d1  movups  xmm0, xmmword ptr cs:_GUID_c5267a7c_640e_5cfc_a7cc_401ccf426e36.Data1
0x1800125d8  movdqu  xmmword ptr [rax+20h], xmm0
0x1800125dd  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@U?$CloakedIid@UIVersionedVector@Internal@Collections@Foundation@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x1800125e2  mov     dword ptr [rdi], 4
0x1800125e8  xor     eax, eax
0x1800125ea  mov     [rbx], r8
0x1800125ed  mov     rbx, [rsp+28h+arg_0]
0x1800125f2  add     rsp, 20h
0x1800125f6  pop     rdi
0x1800125f7  retn
```
