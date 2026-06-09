# _CIVIAudioFilter::CreateInstance_::_1_::dtor$1

- ea: `0x1800889d0`
- end: `0x1800889dc`
- name: `_CIVIAudioFilter::CreateInstance_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000a990`

## pseudocode

```c
__int64 __fastcall CIVIAudioFilter::CreateInstance_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return wil::com_ptr_t<IBaseFilter,wil::err_returncode_policy>::~com_ptr_t<IBaseFilter,wil::err_returncode_policy>((__int64 *)(a2 + 112));
}

```

## disassembly

```asm
0x1800889d0  lea     rcx, [rdx+70h]
0x1800889d7  jmp     ??1?$com_ptr_t@UIBaseFilter@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IBaseFilter,wil::err_returncode_policy>::~com_ptr_t<IBaseFilter,wil::err_returncode_policy>(void)
```
