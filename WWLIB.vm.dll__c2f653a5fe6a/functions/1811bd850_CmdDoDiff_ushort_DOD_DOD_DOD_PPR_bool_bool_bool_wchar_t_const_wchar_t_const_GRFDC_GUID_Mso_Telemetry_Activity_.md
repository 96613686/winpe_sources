# CmdDoDiff(ushort,DOD *,DOD *,DOD *,PPR * *,bool *,bool *,bool *,wchar_t const *,wchar_t const *,GRFDC,_GUID,Mso::Telemetry::Activity *,MsoReserveTag *,MsoReserveTag)

- ea: `0x1811bd850`
- end: `0x1811be818`
- name: `?CmdDoDiff@@YA?AW4CMD@@GPEAVDOD@@00PEAPEAUPPR@@PEA_N22PEB_W3UGRFDC@@U_GUID@@PEAUActivity@Telemetry@Mso@@PEAVMsoReserveTag@@V9@@Z`
- size: `4040`
- prototype: `enum CMD __high(unsigned __int16, struct DOD *, struct DOD *, struct DOD *, struct PPR **, bool *, bool *, bool *, const wchar_t *, const wchar_t *, struct GRFDC, struct _GUID, struct Mso::Telemetry::Activity *, struct MsoReserveTag *, struct MsoReserveTag)`
- caller_count: `9`
- callee_count: `38`
- tags: `broker_com_uri`

## callers

- `0x180b44944`
- `0x1811bd7b0`
- `0x1811be818`
- `0x1817535fc`
- `0x181756598`
- `0x181ba2cb0`
- `0x181e59ec0`
- `0x181e5a260`
- `0x181ef1ad0`

## callees

- `0x18005ac5c`
- `0x180066138`
- `0x18006d7ac`
- `0x1800723b0`
- `0x18009a214`
- `0x1800ae7d4`
- `0x1800ae850`
- `0x180100c70`
- `0x1801914bc`
- `0x180192e74`
- `0x180284294`
- `0x1802b559c`
- `0x1803c05e0`
- `0x180431480`
- `0x180435724`
- `0x18043a3e0`
- `0x18043a458`
- `0x18043a6b0`
- `0x1804406b0`
- `0x18053b430`
- `0x1805d098c`
- `0x180630368`
- `0x18077609c`
- `0x18090faf0`
- `0x1809c1318`
- `0x1809ef9c4`
- `0x180a4c87c`
- `0x180a5ad00`
- `0x180ff5ca0`
- `0x1810795d0`
- `0x181095944`
- `0x1810adec8`
- `0x1810ea1d0`
- `0x18115d3cc`
- `0x1811a9d60`
- `0x1811bd850`
- `0x1811be818`
- `0x1811beda4`

## import_xrefs

- `KERNEL32!SetThreadExecutionState` at `0x1811be002`
- `KERNEL32!SetThreadExecutionState` at `0x1811be0c2`
- `KERNEL32!SetThreadExecutionState` at `0x1811be002`
- `KERNEL32!SetThreadExecutionState` at `0x1811be0c2`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x1811be7ed`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x1811be7ed`
- `Mso20Win32Client!__imp_?SendWarningTag@Diagnostics@Mso@@YAXKW4Category@Logging@2@@Z` at `0x1811bdb20`
- `Mso20Win32Client!__imp_?SendWarningTag@Diagnostics@Mso@@YAXKW4Category@Logging@2@@Z` at `0x1811bde9e`
- `Mso20Win32Client!__imp_?SendWarningTag@Diagnostics@Mso@@YAXKW4Category@Logging@2@@Z` at `0x1811be0e3`
- `Mso20Win32Client!__imp_?SendWarningTag@Diagnostics@Mso@@YAXKW4Category@Logging@2@@Z` at `0x1811bdb20`
- `Mso20Win32Client!__imp_?SendWarningTag@Diagnostics@Mso@@YAXKW4Category@Logging@2@@Z` at `0x1811bde9e`
- `Mso20Win32Client!__imp_?SendWarningTag@Diagnostics@Mso@@YAXKW4Category@Logging@2@@Z` at `0x1811be0e3`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811bdb61`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811bdbb7`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811bdbd9`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811bdc00`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811bdc32`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811bdc64`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811bdc91`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811bdcd0`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811bdcf3`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811bdd16`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811bdd3f`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811bdd6e`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811bdd97`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811bddc9`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811bddf2`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811bde1f`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811bde70`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811bdf16`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811bdf3c`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811be1b9`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811be1dd`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811be1fb`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811be219`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811be237`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811be404`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811be428`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811be447`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811be467`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811be487`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811be4a7`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811be4c7`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811be4e6`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811be506`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811be525`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811be545`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811be565`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811be585`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811be5a5`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811be5d5`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811be61c`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811be63d`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811be65f`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811be680`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811be6a2`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811be6d0`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811be7ab`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811be7ce`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811bdb61`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811bdbb7`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811bdbd9`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811bdc00`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811bdc32`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811bdc64`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811bdc91`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811bdcd0`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811bdcf3`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811bdd16`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811bdd3f`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811bdd6e`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811bdd97`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811bddc9`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811bddf2`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811bde1f`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811bde70`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811bdf16`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811bdf3c`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811be1b9`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811be1dd`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811be1fb`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811be219`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811be237`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811be404`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811be428`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811be447`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811be467`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811be487`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811be4a7`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811be4c7`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811be4e6`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811be506`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811be525`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811be545`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811be565`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811be585`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811be5a5`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811be5d5`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811be61c`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811be63d`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811be65f`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811be680`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811be6a2`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811be6d0`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811be7ab`
- `Mso20Win32Client!__imp_?DataFields@Activity@Telemetry@Mso@@QEAAAEAUIDataFieldCollection@23@XZ` at `0x1811be7ce`
- `Mso20Win32Client!__imp_?Success@Activity@Telemetry@Mso@@QEAAAEAV?$optional@_N@std@@XZ` at `0x1811be603`
- `Mso20Win32Client!__imp_?Success@Activity@Telemetry@Mso@@QEAAAEAV?$optional@_N@std@@XZ` at `0x1811be603`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1811bdb4f`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1811bdff3`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1811be0b3`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1811be256`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1811be338`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1811bdb4f`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1811bdff3`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1811be0b3`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1811be256`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1811be338`

## string_xrefs

- `0x1811be50f`: `cBrokenCommentThreads`
- `0x1811bdb6d`: `SkipUnnecessaryCompareV3`
- `0x1811be1c5`: `ThreadKernelCPUDurationMicrosec`
- `0x1811bde35`: `FIsMainThread`
- `0x1811be25f`: `DisableScreenSaverDuringMerge`
- `0x1811be204`: `ThreadUserCPUDurationMicrosec`

## pseudocode

```c

```
