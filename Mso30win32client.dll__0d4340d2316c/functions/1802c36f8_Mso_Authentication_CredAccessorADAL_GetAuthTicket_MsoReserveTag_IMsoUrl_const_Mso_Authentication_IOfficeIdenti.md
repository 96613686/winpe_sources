# Mso::Authentication::CredAccessorADAL::GetAuthTicket(MsoReserveTag,IMsoUrl const &,Mso::Authentication::IOfficeIdentity * &,bool,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x1802c36f8`
- end: `0x1802c514c`
- name: `?GetAuthTicket@CredAccessorADAL@Authentication@Mso@@AEBA?AV?$Either@W4CredPreparationStatus@@VServiceTicket@Authentication@Mso@@@Collections@3@VMsoReserveTag@@AEBUIMsoUrl@@AEAPEAUIOfficeIdentity@23@_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `6740`
- prototype: `__int64 __usercall@<rax>(Mso::Authentication::CredAccessorADAL *this@<rcx>, __int64, char, __int64)`
- caller_count: `3`
- callee_count: `51`
- tags: `service_task, broker_com_uri`

## callers

- `0x1802683c0`
- `0x180510c00`
- `0x1806106b0`

## callees

- `0x180003de8`
- `0x18001dae0`
- `0x1800218cc`
- `0x1800353cc`
- `0x1800356e4`
- `0x180036858`
- `0x180036984`
- `0x180036a9c`
- `0x180036ca0`
- `0x1800396d0`
- `0x18003a8d0`
- `0x18003b080`
- `0x18003b330`
- `0x1800615e0`
- `0x1800648b8`
- `0x180067830`
- `0x18006e208`
- `0x180080354`
- `0x1800a06fc`
- `0x180110a18`
- `0x1801907f4`
- `0x1801924d8`
- `0x180192520`
- `0x180192560`
- `0x1801ccd48`
- `0x180206870`
- `0x180206910`
- `0x1802469b0`
- `0x180248030`
- `0x1802698cc`
- `0x18026a860`
- `0x18026ab20`
- `0x18026b340`
- `0x1802c2ff8`
- `0x1802c36f8`
- `0x1802c514c`
- `0x1802c53d8`
- `0x1802c5480`
- `0x1802c5514`
- `0x1802c615c`
- `0x1802c6458`
- `0x180391228`
- `0x1803a2ff0`
- `0x18041ba48`
- `0x180500830`
- `0x180500a50`
- `0x18050650c`
- `0x180510e50`
- `0x18057c8bc`
- `0x18068651c`

## import_xrefs

- `Mso20Win32Client!__imp_?ToString@OGuid@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@_N@Z` at `0x1802c3af8`
- `Mso20Win32Client!__imp_?ToString@OGuid@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@_N@Z` at `0x1802c4619`
- `Mso20Win32Client!__imp_?ToString@OGuid@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@_N@Z` at `0x1802c3af8`
- `Mso20Win32Client!__imp_?ToString@OGuid@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@_N@Z` at `0x1802c4619`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1802c3c6e`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1802c3c80`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1802c427d`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1802c4e03`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1802c3c6e`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1802c3c80`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1802c427d`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1802c4e03`
- `Mso20Win32Client!__imp_?GetCurrentCorrelation@Logging@Mso@@YA?AU_GUID@@XZ` at `0x1802c376c`
- `Mso20Win32Client!__imp_?GetCurrentCorrelation@Logging@Mso@@YA?AU_GUID@@XZ` at `0x1802c376c`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1802c410c`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1802c411a`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1802c44c5`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1802c44d3`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1802c4592`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1802c45a0`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1802c4826`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1802c4834`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1802c4b25`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1802c4b33`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1802c4d58`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1802c4d66`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1802c4f84`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1802c4f92`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1802c511d`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1802c512b`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1802c410c`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1802c411a`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1802c44c5`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1802c44d3`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1802c4592`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1802c45a0`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1802c4826`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1802c4834`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1802c4b25`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1802c4b33`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1802c4d58`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1802c4d66`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1802c4f84`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1802c4f92`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1802c511d`
- `Mso20Win32Client!__imp_??1MeasureElapsedTime@Measurements@@QEAA@XZ` at `0x1802c512b`
- `Mso20Win32Client!__imp_??0MeasureElapsedTime@Measurements@@QEAA@UMeasurementIdType@1@_N$$QEAVStopwatch@1@@Z` at `0x1802c3829`
- `Mso20Win32Client!__imp_??0MeasureElapsedTime@Measurements@@QEAA@UMeasurementIdType@1@_N$$QEAVStopwatch@1@@Z` at `0x1802c3875`
- `Mso20Win32Client!__imp_??0MeasureElapsedTime@Measurements@@QEAA@UMeasurementIdType@1@_N$$QEAVStopwatch@1@@Z` at `0x1802c3829`
- `Mso20Win32Client!__imp_??0MeasureElapsedTime@Measurements@@QEAA@UMeasurementIdType@1@_N$$QEAVStopwatch@1@@Z` at `0x1802c3875`
- `Mso20Win32Client!__imp_?Create@OGuid@@YA?AU_GUID@@XZ` at `0x1802c37a2`
- `Mso20Win32Client!__imp_?Create@OGuid@@YA?AU_GUID@@XZ` at `0x1802c37a2`
- `MSVCP140!_Mtx_unlock` at `0x1802c43b5`
- `MSVCP140!_Mtx_unlock` at `0x1802c4970`
- `MSVCP140!_Mtx_unlock` at `0x1802c4dd6`
- `MSVCP140!_Mtx_unlock` at `0x1802c4ea0`
- `MSVCP140!_Mtx_unlock` at `0x1802c43b5`
- `MSVCP140!_Mtx_unlock` at `0x1802c4970`
- `MSVCP140!_Mtx_unlock` at `0x1802c4dd6`
- `MSVCP140!_Mtx_unlock` at `0x1802c4ea0`

## string_xrefs

- `0x1802c3755`: `[CredAccessorADAL] GetAuthTicket`
- `0x1802c3fb8`: `No valid ADAL service params found for Resource ID.`

## pseudocode

```c

```
