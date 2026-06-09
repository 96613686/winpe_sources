# AppPlatformFinder::GetSteamApplications(ConfigSettings const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::vector<Application,std::allocator<Application>> &)

- ea: `0x180104984`
- end: `0x180104ce3`
- name: `?GetSteamApplications@AppPlatformFinder@@CAXAEBVConfigSettings@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$vector@VApplication@@V?$allocator@VApplication@@@std@@@4@@Z`
- size: `863`
- prototype: `__int64 __fastcall(struct ConfigSettings *)`
- caller_count: `1`
- callee_count: `27`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800387b4`

## callees

- `0x1800056f0`
- `0x18000b364`
- `0x18000b7cc`
- `0x18000c220`
- `0x18000c24c`
- `0x18000d834`
- `0x180018300`
- `0x180018450`
- `0x180018a60`
- `0x1800197d4`
- `0x18001bd90`
- `0x18001e0d0`
- `0x180022340`
- `0x180037e84`
- `0x180040254`
- `0x1800404c4`
- `0x180041d4c`
- `0x180043598`
- `0x18004662c`
- `0x180059920`
- `0x18005a8bc`
- `0x1800679f8`
- `0x1800fbf88`
- `0x180103a4c`
- `0x180104984`
- `0x180104cec`
- `0x18010585c`

## import_xrefs

- `KERNEL32!FindFirstFileW` at `0x180104bbc`
- `KERNEL32!FindFirstFileW` at `0x180104bbc`
- `KERNEL32!FindNextFileW` at `0x180104c44`
- `KERNEL32!FindNextFileW` at `0x180104c44`

## string_xrefs

- `0x180104b3c`: `Steam app library path: %ws`
- `0x180104cd1`: `base\appcompat\inventory\software\inv2\lib\appplatformfinder.cpp`
- `0x180104b87`: `appmanifest_*.acf`

## pseudocode

```c

```
