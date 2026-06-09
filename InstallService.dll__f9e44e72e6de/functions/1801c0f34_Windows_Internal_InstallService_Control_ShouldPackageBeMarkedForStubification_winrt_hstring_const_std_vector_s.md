# Windows::Internal::InstallService::Control::ShouldPackageBeMarkedForStubification(winrt::hstring const &,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1801c0f34`
- end: `0x1801c1f5a`
- name: `?ShouldPackageBeMarkedForStubification@Control@InstallService@Internal@Windows@@YA_NAEBUhstring@winrt@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAV?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@8@@Z`
- size: `4134`
- prototype: `__int64 __fastcall(struct winrt::hstring *)`
- caller_count: `1`
- callee_count: `34`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1801d0108`

## callees

- `0x180009ea0`
- `0x18001c144`
- `0x18001c964`
- `0x180020868`
- `0x180022298`
- `0x180033a28`
- `0x180036e6c`
- `0x180037200`
- `0x18004320c`
- `0x180044994`
- `0x180044af8`
- `0x1800453a0`
- `0x180045588`
- `0x18006cb88`
- `0x18006cdd8`
- `0x18006cf2c`
- `0x18006cf8c`
- `0x180095b68`
- `0x180102208`
- `0x180102a20`
- `0x18014e8c8`
- `0x1801bdf80`
- `0x1801be1ac`
- `0x1801be4e4`
- `0x1801be67c`
- `0x1801bf50c`
- `0x1801bf590`
- `0x1801bf7b8`
- `0x1801bfbd0`
- `0x1801bfc9c`
- `0x1801bfd00`
- `0x1801c0d5c`
- `0x1801c0f34`
- `0x1801c22ac`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1801c1442`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1801c1442`
- `api-ms-win-ham-apphistory-l1-1-0!HamQueryPackageUsageInfo` at `0x1801c1507`
- `api-ms-win-ham-apphistory-l1-1-0!HamQueryPackageUsageInfo` at `0x1801c1507`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@J@Z` at `0x1801c1e13`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@J@Z` at `0x1801c1e13`
- `msvcp_win!?clear@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z` at `0x1801c0fd2`
- `msvcp_win!?clear@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z` at `0x1801c0fd2`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@I@Z` at `0x1801c101b`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@I@Z` at `0x1801c1357`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@I@Z` at `0x1801c1377`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@I@Z` at `0x1801c1397`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@I@Z` at `0x1801c1c72`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@I@Z` at `0x1801c1c92`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@I@Z` at `0x1801c1cb2`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@I@Z` at `0x1801c1cd2`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@I@Z` at `0x1801c1cf2`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@I@Z` at `0x1801c1d12`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@I@Z` at `0x1801c101b`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@I@Z` at `0x1801c1357`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@I@Z` at `0x1801c1377`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@I@Z` at `0x1801c1397`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@I@Z` at `0x1801c1c72`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@I@Z` at `0x1801c1c92`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@I@Z` at `0x1801c1cb2`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@I@Z` at `0x1801c1cd2`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@I@Z` at `0x1801c1cf2`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@I@Z` at `0x1801c1d12`

## string_xrefs

- `0x1801c11f0`: `onecoreuap\enduser\winstore\installservice\libqueue2\stubs.cpp`
- `0x1801c12ba`: `onecoreuap\enduser\winstore\installservice\libqueue2\stubs.cpp`
- `0x1801c13a6`: `onecoreuap\enduser\winstore\installservice\libqueue2\stubs.cpp`
- `0x1801c11d8`: `Windows::Internal::InstallService::Control::ShouldPackageBeMarkedForStubification`
- `0x1801c12a2`: `Windows::Internal::InstallService::Control::ShouldPackageBeMarkedForStubification`
- `0x1801c139f`: `Windows::Internal::InstallService::Control::ShouldPackageBeMarkedForStubification`
- `0x1801c145f`: `Convert String Sid to PSID failed, skipping app usage check for this sid.`
- `0x1801c1450`: `Convert String Sid to PSID failed, skipping,`
- `0x1801c133d`: `Install Date:`
- `0x1801c11bd`: `App Install Time longer than threshold.`
- `0x1801c1287`: `App Install Time shorter than threshold.`

## pseudocode

```c

```
