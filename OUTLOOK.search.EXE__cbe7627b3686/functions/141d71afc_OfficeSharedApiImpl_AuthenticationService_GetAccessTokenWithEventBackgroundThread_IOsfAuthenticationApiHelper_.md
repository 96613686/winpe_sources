# OfficeSharedApiImpl::AuthenticationService::GetAccessTokenWithEventBackgroundThread(IOsfAuthenticationApiHelper *,Mso::TCntPtr<IOsfSolutionReference> const &,bool,unsigned __int64,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,Mso::Authentication::IOfficeIdentity *)

- ea: `0x141d71afc`
- end: `0x141d725a1`
- name: `?GetAccessTokenWithEventBackgroundThread@AuthenticationService@OfficeSharedApiImpl@@CAJPEAUIOsfAuthenticationApiHelper@@AEBV?$TCntPtr@UIOsfSolutionReference@@@Mso@@_N_KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@44444PEAUIOfficeIdentity@Authentication@5@@Z`
- size: `2725`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, void *Src, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `23`
- tags: `service_task`

## callers

- `0x141d6f370`

## callees

- `0x140020a9c`
- `0x140020eb0`
- `0x140020fdc`
- `0x1400213e0`
- `0x1400255e8`
- `0x140030910`
- `0x140030a88`
- `0x14007131c`
- `0x140388500`
- `0x1405049f0`
- `0x1407e9990`
- `0x1407eceb0`
- `0x140839730`
- `0x140878408`
- `0x140bc32e0`
- `0x141d6f460`
- `0x141d6f800`
- `0x141d71afc`
- `0x141d73b1c`
- `0x141d73c3c`
- `0x141d8e6b0`
- `0x141d8edd8`
- `0x141d8f178`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x141d72151`
- `OLEAUT32!__imp_SysFreeString` at `0x141d721ff`
- `OLEAUT32!__imp_SysFreeString` at `0x141d722a8`
- `OLEAUT32!__imp_SysFreeString` at `0x141d72344`
- `OLEAUT32!__imp_SysFreeString` at `0x141d723e8`
- `OLEAUT32!__imp_SysFreeString` at `0x141d72480`
- `OLEAUT32!__imp_SysFreeString` at `0x141d72151`
- `OLEAUT32!__imp_SysFreeString` at `0x141d721ff`
- `OLEAUT32!__imp_SysFreeString` at `0x141d722a8`
- `OLEAUT32!__imp_SysFreeString` at `0x141d72344`
- `OLEAUT32!__imp_SysFreeString` at `0x141d723e8`
- `OLEAUT32!__imp_SysFreeString` at `0x141d72480`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141d71cfa`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141d71ddb`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141d71e7b`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141d71f49`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141d720ab`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141d721a9`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141d72257`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141d72300`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141d723a5`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141d72442`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141d724d8`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141d7255f`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141d72574`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141d71cfa`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141d71ddb`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141d71e7b`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141d71f49`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141d720ab`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141d721a9`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141d72257`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141d72300`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141d723a5`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141d72442`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141d724d8`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141d7255f`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141d72574`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x141d71cef`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x141d71dd0`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x141d71e70`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x141d71f3e`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x141d720a0`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x141d7219e`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x141d7224c`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x141d722f5`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x141d72391`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x141d72437`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x141d724cd`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x141d72554`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x141d72569`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x141d71cef`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x141d71dd0`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x141d71e70`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x141d71f3e`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x141d720a0`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x141d7219e`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x141d7224c`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x141d722f5`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x141d72391`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x141d72437`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x141d724cd`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x141d72554`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x141d72569`
- `Mso20Win32Client!__imp_?StartCorrelation@Logging@Mso@@YAXXZ` at `0x141d71bcc`
- `Mso20Win32Client!__imp_?StartCorrelation@Logging@Mso@@YAXXZ` at `0x141d71bcc`

## string_xrefs

- `0x141d71b8c`: `GetAccessTokenV3Background`

## pseudocode

```c

```
