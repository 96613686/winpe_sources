# Microsoft::WRL::ComPtr<Windows::Devices::Geolocation::IGeopoint>::~ComPtr<Windows::Devices::Geolocation::IGeopoint>(void)

- ea: `0x180006f00`
- end: `0x180006f05`
- name: `??1?$ComPtr@UIGeopoint@Geolocation@Devices@Windows@@@WRL@Microsoft@@QEAA@XZ`
- size: `5`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `21`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180027aea`
- `0x18002811b`
- `0x18002812d`
- `0x18002813f`
- `0x180028151`
- `0x180028175`
- `0x18002894c`
- `0x180028970`
- `0x1800289ee`
- `0x180028b40`
- `0x180028b76`
- `0x180028bac`
- `0x180028bbe`
- `0x180028bd0`
- `0x180028bf4`
- `0x180029225`
- `0x18002927f`
- `0x1800292b5`
- `0x1800292c7`
- `0x1800292d9`
- `0x180029d84`

## callees

- `0x180009fc0`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall Microsoft::WRL::ComPtr<Windows::Devices::Geolocation::IGeopoint>::~ComPtr<Windows::Devices::Geolocation::IGeopoint>(
        __int64 a1)
{
  return Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1);
}

```

## disassembly

```asm
0x180006f00  jmp     ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
```
