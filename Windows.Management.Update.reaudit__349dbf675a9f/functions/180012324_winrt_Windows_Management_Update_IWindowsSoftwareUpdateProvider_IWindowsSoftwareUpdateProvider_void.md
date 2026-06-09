# winrt::Windows::Management::Update::IWindowsSoftwareUpdateProvider::~IWindowsSoftwareUpdateProvider(void)

- ea: `0x180012324`
- end: `0x180012339`
- name: `??1IWindowsSoftwareUpdateProvider@Update@Management@Windows@winrt@@QEAA@XZ`
- size: `21`
- prototype: `void __fastcall(winrt::Windows::Management::Update::IWindowsSoftwareUpdateProvider *__hidden this)`
- caller_count: `79`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180017c58`
- `0x180028fba`
- `0x180028fe2`
- `0x18002900a`
- `0x18002906c`
- `0x180029082`
- `0x180029098`
- `0x1800290ae`
- `0x1800290da`
- `0x180029102`
- `0x180029118`
- `0x18002912e`
- `0x180029498`
- `0x1800294ae`
- `0x1800294c4`
- `0x180029545`
- `0x18002a0fb`
- `0x18002a143`
- `0x18002a179`
- `0x18002a1af`
- `0x18002a1e5`
- `0x18002a21b`
- `0x18002a251`
- `0x18002a287`
- `0x18002a2bd`
- `0x18002a2f3`
- `0x18002a317`
- `0x18002a33b`
- `0x18002a34d`
- `0x18002a383`
- `0x18002a395`
- `0x18002a3cb`
- `0x18002a3dd`
- `0x18002a401`
- `0x18002a425`
- `0x18002a437`
- `0x18002a46d`
- `0x18002a47f`
- `0x18002a4b5`
- `0x18002a4c7`
- `0x18002a4eb`
- `0x18002a50f`
- `0x18002a521`
- `0x18002a557`
- `0x18002a569`
- `0x18002a59f`
- `0x18002a5b1`
- `0x18002a5e7`
- `0x18002a614`
- `0x18002a644`

## callees

- `0x180012324`
- `0x180017c3c`

## pseudocode

```c
void __fastcall winrt::Windows::Management::Update::IWindowsSoftwareUpdateProvider::~IWindowsSoftwareUpdateProvider(
        winrt::Windows::Management::Update::IWindowsSoftwareUpdateProvider *this)
{
  if ( *(_QWORD *)this )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(this);
}

```

## disassembly

```asm
0x180012324  sub     rsp, 28h
0x180012328  cmp     qword ptr [rcx], 0
0x18001232c  jz      short loc_180012333
0x18001232e  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180012333  add     rsp, 28h
0x180012337  retn
```
