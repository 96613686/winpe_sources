# winrt::Windows::Foundation::IAsyncAction::~IAsyncAction(void)

- ea: `0x180005b54`
- end: `0x180005b68`
- name: `??1IAsyncAction@Foundation@Windows@winrt@@QEAA@XZ`
- size: `20`
- prototype: `void __fastcall(winrt::Windows::Foundation::IAsyncAction *__hidden this)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180010417`
- `0x18001044d`
- `0x180010d1a`
- `0x180010d2c`
- `0x180010d3e`
- `0x180010df5`

## callees

- `0x180005b54`
- `0x18000f544`

## pseudocode

```c
void __fastcall winrt::Windows::Foundation::IAsyncAction::~IAsyncAction(winrt::Windows::Foundation::IAsyncAction *this)
{
  if ( *(_QWORD *)this )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(this);
}

```

## disassembly

```asm
0x180005b54  sub     rsp, 28h
0x180005b58  cmp     qword ptr [rcx], 0
0x180005b5c  jz      short loc_180005B63
0x180005b5e  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180005b63  add     rsp, 28h
0x180005b67  retn
```
