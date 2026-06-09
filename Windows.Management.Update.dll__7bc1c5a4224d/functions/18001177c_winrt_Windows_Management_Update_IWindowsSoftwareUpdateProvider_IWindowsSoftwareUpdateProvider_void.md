# winrt::Windows::Management::Update::IWindowsSoftwareUpdateProvider::~IWindowsSoftwareUpdateProvider(void)

- ea: `0x18001177c`
- end: `0x180011790`
- name: `??1IWindowsSoftwareUpdateProvider@Update@Management@Windows@winrt@@QEAA@XZ`
- size: `20`
- prototype: `void __fastcall(winrt::Windows::Management::Update::IWindowsSoftwareUpdateProvider *__hidden this)`
- caller_count: `42`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180017004`
- `0x180027a5a`
- `0x180027a82`
- `0x180027aaa`
- `0x180027b0c`
- `0x180027b22`
- `0x180027b38`
- `0x180027b4e`
- `0x180027b64`
- `0x180027b7a`
- `0x180027b90`
- `0x180027ba6`
- `0x180027be4`
- `0x180027bfa`
- `0x180027c10`
- `0x180027f70`
- `0x180027f86`
- `0x180027f9c`
- `0x18002874d`
- `0x180028795`
- `0x1800287b9`
- `0x1800287e5`
- `0x180028811`
- `0x180028835`
- `0x18002888f`
- `0x1800288c5`
- `0x1800288f4`
- `0x180028935`
- `0x180028964`
- `0x180028993`
- `0x1800289ea`
- `0x180028a00`
- `0x180028a28`
- `0x180028a3a`
- `0x180028a4c`
- `0x180028cb4`
- `0x180028d5e`
- `0x180028e26`
- `0x180028e3c`
- `0x180028ed3`
- `0x180028ee5`
- `0x180029014`

## callees

- `0x18001177c`
- `0x180016fe4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall winrt::Windows::Management::Update::IWindowsSoftwareUpdateProvider::~IWindowsSoftwareUpdateProvider(
        winrt::Windows::Management::Update::IWindowsSoftwareUpdateProvider *this)
{
  if ( *(_QWORD *)this )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(this);
}

```

## disassembly

```asm
0x18001177c  sub     rsp, 28h
0x180011780  cmp     qword ptr [rcx], 0
0x180011784  jz      short loc_18001178B
0x180011786  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001178b  add     rsp, 28h
0x18001178f  retn
```
