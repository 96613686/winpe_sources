# OfficeSharedApiImpl::AuthenticationService::GetAccessTokenWithEventBackgroundThread(IOsfAuthenticationApiHelper *,Mso::TCntPtr<IOsfSolutionReference> const &,bool,unsigned __int64,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,Mso::Authentication::IOfficeIdentity *)

- ea: `0x141d71a3c`
- end: `0x141d724e1`
- name: `?GetAccessTokenWithEventBackgroundThread@AuthenticationService@OfficeSharedApiImpl@@CAJPEAUIOsfAuthenticationApiHelper@@AEBV?$TCntPtr@UIOsfSolutionReference@@@Mso@@_N_KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@44444PEAUIOfficeIdentity@Authentication@5@@Z`
- size: `2725`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, void *Src, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `23`
- tags: `service_task`

## callers

- `0x141d6f2b0`

## callees

- `0x140020a9c`
- `0x140020eb0`
- `0x140020fdc`
- `0x1400213e0`
- `0x1400255e8`
- `0x140030910`
- `0x140030a88`
- `0x1400712cc`
- `0x140387bf0`
- `0x140503f00`
- `0x1407e99f0`
- `0x1407ecf10`
- `0x140839790`
- `0x140878418`
- `0x140bc3220`
- `0x141d6f3a0`
- `0x141d6f740`
- `0x141d71a3c`
- `0x141d73a5c`
- `0x141d73b7c`
- `0x141d8e5f0`
- `0x141d8ed18`
- `0x141d8f0b8`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x141d72091`
- `OLEAUT32!__imp_SysFreeString` at `0x141d7213f`
- `OLEAUT32!__imp_SysFreeString` at `0x141d721e8`
- `OLEAUT32!__imp_SysFreeString` at `0x141d72284`
- `OLEAUT32!__imp_SysFreeString` at `0x141d72328`
- `OLEAUT32!__imp_SysFreeString` at `0x141d723c0`
- `OLEAUT32!__imp_SysFreeString` at `0x141d72091`
- `OLEAUT32!__imp_SysFreeString` at `0x141d7213f`
- `OLEAUT32!__imp_SysFreeString` at `0x141d721e8`
- `OLEAUT32!__imp_SysFreeString` at `0x141d72284`
- `OLEAUT32!__imp_SysFreeString` at `0x141d72328`
- `OLEAUT32!__imp_SysFreeString` at `0x141d723c0`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141d71c3a`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141d71d1b`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141d71dbb`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141d71e89`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141d71feb`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141d720e9`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141d72197`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141d72240`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141d722e5`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141d72382`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141d72418`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141d7249f`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141d724b4`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141d71c3a`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141d71d1b`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141d71dbb`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141d71e89`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141d71feb`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141d720e9`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141d72197`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141d72240`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141d722e5`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141d72382`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141d72418`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141d7249f`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x141d724b4`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x141d71c2f`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x141d71d10`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x141d71db0`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x141d71e7e`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x141d71fe0`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x141d720de`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x141d7218c`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x141d72235`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x141d722d1`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x141d72377`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x141d7240d`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x141d72494`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x141d724a9`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x141d71c2f`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x141d71d10`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x141d71db0`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x141d71e7e`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x141d71fe0`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x141d720de`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x141d7218c`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x141d72235`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x141d722d1`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x141d72377`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x141d7240d`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x141d72494`
- `Mso20Win32Client!__imp_?EndCurrentCorrelation@Logging@Mso@@YAXXZ` at `0x141d724a9`
- `Mso20Win32Client!__imp_?StartCorrelation@Logging@Mso@@YAXXZ` at `0x141d71b0c`
- `Mso20Win32Client!__imp_?StartCorrelation@Logging@Mso@@YAXXZ` at `0x141d71b0c`

## string_xrefs

- `0x141d71acc`: `GetAccessTokenV3Background`

## pseudocode

```c

```
