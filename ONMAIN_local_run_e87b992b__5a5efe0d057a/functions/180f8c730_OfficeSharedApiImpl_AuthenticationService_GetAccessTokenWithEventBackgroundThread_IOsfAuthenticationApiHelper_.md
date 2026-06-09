# OfficeSharedApiImpl::AuthenticationService::GetAccessTokenWithEventBackgroundThread(IOsfAuthenticationApiHelper *,Mso::TCntPtr<IOsfSolutionReference> const &,bool,unsigned __int64,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,Mso::Authentication::IOfficeIdentity *)

- ea: `0x180f8c730`
- end: `0x180f8d1ec`
- name: `?GetAccessTokenWithEventBackgroundThread@AuthenticationService@OfficeSharedApiImpl@@CAJPEAUIOsfAuthenticationApiHelper@@AEBV?$TCntPtr@UIOsfSolutionReference@@@Mso@@_N_KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@44444PEAUIOfficeIdentity@Authentication@5@@Z`
- size: `2748`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `service_task`

## callers

- `0x180f8bcd0`

## callees

- `0x18002da60`
- `0x18005cab0`
- `0x18006eaec`
- `0x1800718e0`
- `0x180081214`
- `0x180094038`
- `0x18009414c`
- `0x180094170`
- `0x1802e0c78`
- `0x1802e2190`
- `0x1802e3f10`
- `0x1802e5170`
- `0x1802e5190`
- `0x180325e60`
- `0x1804cb54c`
- `0x1804cbc68`
- `0x1804cbfa8`
- `0x1804cbff4`
- `0x1804ccd60`
- `0x1804dc5c4`
- `0x180f8bdc0`
- `0x180f8c160`
- `0x180f8c730`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180f8cd99`
- `OLEAUT32!__imp_SysFreeString` at `0x180f8ce47`
- `OLEAUT32!__imp_SysFreeString` at `0x180f8cef0`
- `OLEAUT32!__imp_SysFreeString` at `0x180f8cf8c`
- `OLEAUT32!__imp_SysFreeString` at `0x180f8d027`
- `OLEAUT32!__imp_SysFreeString` at `0x180f8d0bd`
- `OLEAUT32!__imp_SysFreeString` at `0x180f8cd99`
- `OLEAUT32!__imp_SysFreeString` at `0x180f8ce47`
- `OLEAUT32!__imp_SysFreeString` at `0x180f8cef0`
- `OLEAUT32!__imp_SysFreeString` at `0x180f8cf8c`
- `OLEAUT32!__imp_SysFreeString` at `0x180f8d027`
- `OLEAUT32!__imp_SysFreeString` at `0x180f8d0bd`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x180f8c92e`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x180f8ca32`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x180f8caca`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x180f8cb98`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x180f8ccf3`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x180f8cdf1`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x180f8ce9f`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x180f8cf48`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x180f8cfe4`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x180f8d07f`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x180f8d115`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x180f8d19c`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x180f8d1bf`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x180f8c92e`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x180f8ca32`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x180f8caca`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x180f8cb98`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x180f8ccf3`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x180f8cdf1`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x180f8ce9f`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x180f8cf48`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x180f8cfe4`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x180f8d07f`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x180f8d115`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x180f8d19c`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x180f8d1bf`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x180f8c923`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x180f8ca27`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x180f8cabf`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x180f8cb8d`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x180f8cce8`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x180f8cde6`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x180f8ce94`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x180f8cf3d`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x180f8cfd9`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x180f8d074`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x180f8d10a`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x180f8d191`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x180f8d1b4`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x180f8c923`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x180f8ca27`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x180f8cabf`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x180f8cb8d`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x180f8cce8`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x180f8cde6`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x180f8ce94`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x180f8cf3d`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x180f8cfd9`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x180f8d074`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x180f8d10a`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x180f8d191`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x180f8d1b4`
- `Mso20Win32Client!__imp_?StartCorrelation@Logging@Mso@@YAXXZ` at `0x180f8c800`
- `Mso20Win32Client!__imp_?StartCorrelation@Logging@Mso@@YAXXZ` at `0x180f8c800`

## string_xrefs

- `0x180f8c7c0`: `GetAccessTokenV3Background`

## pseudocode

```c

```
