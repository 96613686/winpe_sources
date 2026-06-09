# Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *>>::~ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *>>(void)

- ea: `0x180004420`
- end: `0x180004448`
- name: `??1?$ComPtr@U?$VectorChangedEventHandler@PEAUISettingItem@DataModel@SystemSettings@@@Collections@Foundation@Windows@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: `void(void *)`
- caller_count: `13`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800297d1`
- `0x1800297f5`
- `0x180029a17`
- `0x180029c60`
- `0x180029cdc`
- `0x180029d00`
- `0x180029d24`
- `0x180029d48`
- `0x180029d5a`
- `0x180029d6c`
- `0x180029d7e`
- `0x18002a440`
- `0x18002a6af`

## callees

- `0x180004420`
- `0x18002b010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *>>::~ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<SystemSettings::DataModel::ISettingItem *>>(
        __int64 *a1)
{
  __int64 v2; // rcx

  v2 = *a1;
  if ( v2 )
  {
    *a1 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
}

```

## disassembly

```asm
0x180004420  sub     rsp, 28h
0x180004424  mov     rax, rcx
0x180004427  mov     rcx, [rcx]
0x18000442a  test    rcx, rcx
0x18000442d  jz      short loc_180004443
0x18000442f  mov     qword ptr [rax], 0
0x180004436  mov     rax, [rcx]
0x180004439  mov     rax, [rax+10h]
0x18000443d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004442  nop
0x180004443  add     rsp, 28h
0x180004447  retn
```
