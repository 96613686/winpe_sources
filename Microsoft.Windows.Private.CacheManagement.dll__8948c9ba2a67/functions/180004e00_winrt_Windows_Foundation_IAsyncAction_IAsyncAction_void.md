# winrt::Windows::Foundation::IAsyncAction::~IAsyncAction(void)

- ea: `0x180004e00`
- end: `0x180004e0b`
- name: `??1IAsyncAction@Foundation@Windows@winrt@@QEAA@XZ`
- size: `11`
- prototype: `void __fastcall(winrt::Windows::Foundation::IAsyncAction *__hidden this)`
- caller_count: `48`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001d990`
- `0x18001d9b0`
- `0x18001dbe9`
- `0x18001dcb5`
- `0x18001dce8`
- `0x18001dcf4`
- `0x18001dd00`
- `0x18001dd26`
- `0x18001dd32`
- `0x18001dd3e`
- `0x18001dddc`
- `0x18001dde8`
- `0x18001ddf4`
- `0x18001de1f`
- `0x18001de2b`
- `0x18001de56`
- `0x18001de62`
- `0x18001de6e`
- `0x18001de7a`
- `0x18001de86`
- `0x18001de9e`
- `0x18001dec2`
- `0x18001dece`
- `0x18001dee6`
- `0x18001def2`
- `0x18001df0a`
- `0x18001df22`
- `0x18001df2e`
- `0x18001df50`
- `0x18001df5c`
- `0x18001df70`
- `0x18001df96`
- `0x18001dfe0`
- `0x18001dfec`
- `0x18001e010`
- `0x18001e01c`
- `0x18001e028`
- `0x18001e040`
- `0x18001e04c`
- `0x18001e058`
- `0x18001e064`
- `0x18001e088`
- `0x18001e0a0`
- `0x18001e0b8`
- `0x18001e0c4`
- `0x18001e410`
- `0x18001e870`
- `0x18001e890`

## callees

- `0x180003840`

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
0x180004e00  cmp     qword ptr [rcx], 0
0x180004e04  jnz     ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180004e0a  retn
```
