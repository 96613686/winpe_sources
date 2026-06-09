# winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)

- ea: `0x180011e0c`
- end: `0x180011e25`
- name: `?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ`
- size: `25`
- prototype: ``
- caller_count: `27`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000b10c`
- `0x18000b8fc`
- `0x18000bafc`
- `0x18000bc5c`
- `0x18000c050`
- `0x18000c140`
- `0x18000c264`
- `0x18000c354`
- `0x18000c974`
- `0x18000ce6c`
- `0x18000d000`
- `0x18000d118`
- `0x18000d188`
- `0x18000d1f8`
- `0x18000d36c`
- `0x18000d418`
- `0x18000d5a0`
- `0x18000e950`
- `0x18000fa80`
- `0x18000fac0`
- `0x180010560`
- `0x180011044`
- `0x1800115e4`
- `0x180011cac`
- `0x180012791`
- `0x180012895`
- `0x180012999`

## callees

- `0x180013010`

## pseudocode

```c
__int64 __fastcall winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(
        __int64 *a1)
{
  __int64 v1; // rdx

  v1 = *a1;
  *a1 = 0;
  return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
}

```

## disassembly

```asm
0x180011e0c  mov     rdx, [rcx]
0x180011e0f  mov     qword ptr [rcx], 0
0x180011e16  mov     rcx, rdx
0x180011e19  mov     rax, [rdx]
0x180011e1c  mov     rax, [rax+10h]
0x180011e20  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
