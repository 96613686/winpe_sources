# Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Devices::Radios::RadioAccessStatus>>::~ComPtr<Windows::Foundation::IAsyncOperation<Windows::Devices::Radios::RadioAccessStatus>>(void)

- ea: `0x1800036ac`
- end: `0x1800036d5`
- name: `??1?$ComPtr@U?$IAsyncOperation@W4RadioAccessStatus@Radios@Devices@Windows@@@Foundation@Windows@@@WRL@Microsoft@@QEAA@XZ`
- size: `41`
- prototype: ``
- caller_count: `16`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a0a6`
- `0x18000a0b8`
- `0x18000a0ca`
- `0x18000a111`
- `0x18000a123`
- `0x18000a159`
- `0x18000a16b`
- `0x18000a17d`
- `0x18000a18f`
- `0x18000a1a1`
- `0x18000a1b3`
- `0x18000a1c5`
- `0x18000a1d7`
- `0x18000a233`
- `0x18000a6eb`
- `0x18000a6fd`

## callees

- `0x1800036ac`
- `0x18000b010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<enum Windows::Devices::Radios::RadioAccessStatus>>::~ComPtr<Windows::Foundation::IAsyncOperation<enum Windows::Devices::Radios::RadioAccessStatus>>(
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
0x1800036ac  sub     rsp, 28h
0x1800036b0  mov     rax, rcx
0x1800036b3  mov     rcx, [rcx]
0x1800036b6  test    rcx, rcx
0x1800036b9  jz      short loc_1800036CF
0x1800036bb  mov     qword ptr [rax], 0
0x1800036c2  mov     rax, [rcx]
0x1800036c5  mov     rax, [rax+10h]
0x1800036c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036ce  nop
0x1800036cf  add     rsp, 28h
0x1800036d3  retn
```
