# std::pair<DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>::~pair<DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>(void)

- ea: `0x18000a33c`
- end: `0x18000a36f`
- name: `??1?$pair@W4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@QEAA@XZ`
- size: `51`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180022a60`
- `0x180022a80`
- `0x180022aa0`

## callees

- `0x18000a33c`
- `0x180025010`

## pseudocode

```c
__int64 __fastcall std::pair<enum DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>::~pair<enum DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>(
        __int64 a1)
{
  __int64 result; // rax
  __int64 v2; // rcx

  result = a1;
  v2 = *(_QWORD *)(a1 + 8);
  if ( v2 )
  {
    *(_QWORD *)(result + 8) = 0;
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  return result;
}

```

## disassembly

```asm
0x18000a33c  sub     rsp, 38h
0x18000a340  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000a349  mov     rax, rcx
0x18000a34c  mov     rcx, [rcx+8]
0x18000a350  test    rcx, rcx
0x18000a353  jz      short loc_18000A36A
0x18000a355  mov     qword ptr [rax+8], 0
0x18000a35d  mov     rax, [rcx]
0x18000a360  mov     rax, [rax+10h]
0x18000a364  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a369  nop
0x18000a36a  add     rsp, 38h
0x18000a36e  retn
```
