# Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfoEnumerator>::~ComPtr<IAppxBundleManifestPackageInfoEnumerator>(void)

- ea: `0x180009874`
- end: `0x1800098a5`
- name: `??1?$ComPtr@UIAppxBundleManifestPackageInfoEnumerator@@@WRL@Microsoft@@QEAA@XZ`
- size: `49`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180022960`
- `0x180022980`
- `0x180022a00`
- `0x180022a20`
- `0x180022ac0`
- `0x180022c8a`

## callees

- `0x180009874`
- `0x180025010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfoEnumerator>::~ComPtr<IAppxBundleManifestPackageInfoEnumerator>(
        _QWORD *a1)
{
  _QWORD *result; // rax
  __int64 v2; // rcx

  result = a1;
  v2 = *a1;
  if ( v2 )
  {
    *result = 0;
    return (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  return result;
}

```

## disassembly

```asm
0x180009874  sub     rsp, 38h
0x180009878  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180009881  mov     rax, rcx
0x180009884  mov     rcx, [rcx]
0x180009887  test    rcx, rcx
0x18000988a  jz      short loc_1800098A0
0x18000988c  mov     qword ptr [rax], 0
0x180009893  mov     rax, [rcx]
0x180009896  mov     rax, [rax+10h]
0x18000989a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000989f  nop
0x1800098a0  add     rsp, 38h
0x1800098a4  retn
```
