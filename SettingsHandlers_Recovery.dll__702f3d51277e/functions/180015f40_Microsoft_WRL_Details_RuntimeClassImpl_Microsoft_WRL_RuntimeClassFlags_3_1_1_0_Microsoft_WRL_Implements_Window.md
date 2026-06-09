# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::Implements<Windows::Foundation::Collections::IVector<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::IIterable<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::IObservableVector<SystemSettings::DataModel::ISettingItem *>>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x180015f40`
- end: `0x180015fb9`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$Implements@U?$IVector@PEAUISettingItem@DataModel@SystemSettings@@@Collections@Foundation@Windows@@U?$IIterable@PEAUISettingItem@DataModel@SystemSettings@@@234@U?$IObservableVector@PEAUISettingItem@DataModel@SystemSettings@@@234@@23@U?$CloakedIid@UIVersionedVector@Internal@Collections@Foundation@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `121`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180015fc0`
- `0x180015fd0`
- `0x180016050`

## callees

- `0x180015f40`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180015f62`
- `ole32!CoTaskMemAlloc` at `0x180015f62`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::Implements<Windows::Foundation::Collections::IVector<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::IIterable<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::IObservableVector<SystemSettings::DataModel::ISettingItem *>>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>::GetIids(
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
0x180015f40  mov     [rsp+arg_0], rbx
0x180015f45  push    rdi
0x180015f46  sub     rsp, 20h
0x180015f4a  mov     qword ptr [r8], 0
0x180015f51  mov     ecx, 40h ; '@'; cb
0x180015f56  mov     dword ptr [rdx], 0
0x180015f5c  mov     rbx, r8
0x180015f5f  mov     rdi, rdx
0x180015f62  call    cs:__imp_CoTaskMemAlloc
0x180015f68  test    rax, rax
0x180015f6b  jnz     short loc_180015F74
0x180015f6d  mov     eax, 8007000Eh
0x180015f72  jmp     short loc_180015FAE
0x180015f74  movups  xmm0, xmmword ptr cs:_GUID_ca56de18_3714_5673_982e_3ea0322179bc.Data1
0x180015f7b  movdqu  xmmword ptr [rax], xmm0
0x180015f7f  movups  xmm1, xmmword ptr cs:_GUID_2aab4305_70a6_58fc_8050_199102b52440.Data1
0x180015f86  movdqu  xmmword ptr [rax+10h], xmm1
0x180015f8b  movups  xmm0, xmmword ptr cs:_GUID_c5267a7c_640e_5cfc_a7cc_401ccf426e36.Data1
0x180015f92  movdqu  xmmword ptr [rax+20h], xmm0
0x180015f97  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180015f9e  movdqu  xmmword ptr [rax+30h], xmm1
0x180015fa3  mov     dword ptr [rdi], 4
0x180015fa9  mov     [rbx], rax
0x180015fac  xor     eax, eax
0x180015fae  mov     rbx, [rsp+28h+arg_0]
0x180015fb3  add     rsp, 20h
0x180015fb7  pop     rdi
0x180015fb8  retn
```
