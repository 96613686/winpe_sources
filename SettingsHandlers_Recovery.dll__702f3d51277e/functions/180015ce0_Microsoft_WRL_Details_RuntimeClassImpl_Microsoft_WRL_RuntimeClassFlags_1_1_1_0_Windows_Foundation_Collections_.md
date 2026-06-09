# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IVectorView<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::IIterable<SystemSettings::DataModel::ISettingItem *>,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x180015ce0`
- end: `0x180015d4d`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IVectorView@PEAUISettingItem@DataModel@SystemSettings@@@Collections@Foundation@Windows@@U?$IIterable@PEAUISettingItem@DataModel@SystemSettings@@@567@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `109`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180015d60`
- `0x180016000`

## callees

- `0x180015ce0`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180015d02`
- `ole32!CoTaskMemAlloc` at `0x180015d02`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IVectorView<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::IIterable<SystemSettings::DataModel::ISettingItem *>,Microsoft::WRL::FtmBase>::GetIids(
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
0x180015ce0  mov     [rsp+arg_0], rbx
0x180015ce5  push    rdi
0x180015ce6  sub     rsp, 20h
0x180015cea  mov     qword ptr [r8], 0
0x180015cf1  mov     ecx, 30h ; '0'; cb
0x180015cf6  mov     dword ptr [rdx], 0
0x180015cfc  mov     rbx, r8
0x180015cff  mov     rdi, rdx
0x180015d02  call    cs:__imp_CoTaskMemAlloc
0x180015d08  test    rax, rax
0x180015d0b  jnz     short loc_180015D14
0x180015d0d  mov     eax, 8007000Eh
0x180015d12  jmp     short loc_180015D42
0x180015d14  movups  xmm0, xmmword ptr cs:_GUID_2748819e_b5b7_5f54_a337_c04593b19e74.Data1
0x180015d1b  movdqu  xmmword ptr [rax], xmm0
0x180015d1f  movups  xmm1, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x180015d26  movdqu  xmmword ptr [rax+10h], xmm1
0x180015d2b  movups  xmm0, xmmword ptr cs:_GUID_2aab4305_70a6_58fc_8050_199102b52440.Data1
0x180015d32  movdqu  xmmword ptr [rax+20h], xmm0
0x180015d37  mov     dword ptr [rdi], 3
0x180015d3d  mov     [rbx], rax
0x180015d40  xor     eax, eax
0x180015d42  mov     rbx, [rsp+28h+arg_0]
0x180015d47  add     rsp, 20h
0x180015d4b  pop     rdi
0x180015d4c  retn
```
