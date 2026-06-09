# winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)

- ea: `0x18000d000`
- end: `0x18000d014`
- name: `??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ`
- size: `20`
- prototype: ``
- caller_count: `14`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800123de`
- `0x1800123f0`
- `0x180012402`
- `0x180012426`
- `0x18001244a`
- `0x18001245c`
- `0x1800124ac`
- `0x180012606`
- `0x180012632`
- `0x180012644`
- `0x180012656`
- `0x180012668`
- `0x18001267a`
- `0x18001268c`

## callees

- `0x18000d000`
- `0x180011e0c`

## pseudocode

```c
__int64 __fastcall winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(
        __int64 *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1);
  return result;
}

```

## disassembly

```asm
0x18000d000  sub     rsp, 28h
0x18000d004  cmp     qword ptr [rcx], 0
0x18000d008  jz      short loc_18000D00F
0x18000d00a  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000d00f  add     rsp, 28h
0x18000d013  retn
```
