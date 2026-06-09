# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IIterator<SystemSettings::DataModel::ISettingItem *>,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x180015970`
- end: `0x1800159d6`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IIterator@PEAUISettingItem@DataModel@SystemSettings@@@Collections@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `102`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180014af0`
- `0x180015970`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015992`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015992`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IIterator<SystemSettings::DataModel::ISettingItem *>,Microsoft::WRL::FtmBase>::GetIids(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  __int64 v5; // rcx
  LPVOID v6; // r8
  __int64 result; // rax
  __int64 v8; // r8
  int v9; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v6 = CoTaskMemAlloc(0x20u);
  if ( !v6 )
    return 2147942414LL;
  v9 = 0;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IIterator<SystemSettings::DataModel::ISettingItem *>,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    v5,
    &v9,
    v6);
  *a2 = 2;
  result = 0;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x180015970  mov     [rsp+arg_0], rbx
0x180015975  push    rdi
0x180015976  sub     rsp, 20h
0x18001597a  mov     qword ptr [r8], 0
0x180015981  mov     ecx, 20h ; ' '; cb
0x180015986  mov     dword ptr [rdx], 0
0x18001598c  mov     rbx, r8
0x18001598f  mov     rdi, rdx
0x180015992  call    cs:__imp_CoTaskMemAlloc
0x180015999  nop     dword ptr [rax+rax+00h]
0x18001599e  mov     r8, rax
0x1800159a1  test    rax, rax
0x1800159a4  jnz     short loc_1800159AD
0x1800159a6  mov     eax, 8007000Eh
0x1800159ab  jmp     short loc_1800159CA
0x1800159ad  lea     rdx, [rsp+28h+arg_8]
0x1800159b2  mov     [rsp+28h+arg_8], 0
0x1800159ba  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@U?$IIterator@PEAUISettingItem@DataModel@SystemSettings@@@Collections@Foundation@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Foundation::Collections::IIterator<SystemSettings::DataModel::ISettingItem *>,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x1800159bf  mov     dword ptr [rdi], 2
0x1800159c5  xor     eax, eax
0x1800159c7  mov     [rbx], r8
0x1800159ca  mov     rbx, [rsp+28h+arg_0]
0x1800159cf  add     rsp, 20h
0x1800159d3  pop     rdi
0x1800159d4  retn
```
