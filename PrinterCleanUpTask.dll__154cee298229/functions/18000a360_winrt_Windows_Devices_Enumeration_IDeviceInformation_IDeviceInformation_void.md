# winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation(void)

- ea: `0x18000a360`
- end: `0x18000a374`
- name: `??1IDeviceInformation@Enumeration@Devices@Windows@winrt@@QEAA@XZ`
- size: `20`
- prototype: `void __fastcall(winrt::Windows::Devices::Enumeration::IDeviceInformation *__hidden this)`
- caller_count: `51`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800086e0`
- `0x1800087f8`
- `0x180008910`
- `0x180009684`
- `0x180009710`
- `0x1800097d8`
- `0x18000a5b4`
- `0x18000a850`
- `0x18000bfd0`
- `0x18000c120`
- `0x18000c534`
- `0x18000d22c`
- `0x18000d2e8`
- `0x18000d424`
- `0x18000da60`
- `0x18000ea58`
- `0x18000eb14`
- `0x180010e20`
- `0x180010fb8`
- `0x180011060`
- `0x180011954`
- `0x180011a10`
- `0x180011ea8`
- `0x180012bf0`
- `0x180012cac`
- `0x180012e10`
- `0x180012f8c`
- `0x1800144e0`
- `0x180014638`
- `0x1800146f4`
- `0x180015400`
- `0x180015920`
- `0x180015a9c`
- `0x180015d18`
- `0x180016779`
- `0x1800167af`
- `0x1800167d3`
- `0x18001684f`
- `0x180016873`
- `0x180016a50`
- `0x180016a7c`
- `0x180016b7d`
- `0x180016ba1`
- `0x180016bb3`
- `0x180016d47`
- `0x180016d8f`
- `0x180016da1`
- `0x180016e28`
- `0x1800171bc`
- `0x1800172df`

## callees

- `0x18000750c`
- `0x18000a360`

## pseudocode

```c
void __fastcall winrt::Windows::Devices::Enumeration::IDeviceInformation::~IDeviceInformation(
        winrt::Windows::Devices::Enumeration::IDeviceInformation *this)
{
  if ( *(_QWORD *)this )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(this);
}

```

## disassembly

```asm
0x18000a360  sub     rsp, 28h
0x18000a364  cmp     qword ptr [rcx], 0
0x18000a368  jz      short loc_18000A36F
0x18000a36a  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000a36f  add     rsp, 28h
0x18000a373  retn
```
