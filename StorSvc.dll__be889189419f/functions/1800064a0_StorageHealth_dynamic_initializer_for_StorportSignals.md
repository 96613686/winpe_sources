# StorageHealth::_dynamic_initializer_for__StorportSignals__

- ea: `0x1800064a0`
- end: `0x180006d7f`
- name: `StorageHealth::_dynamic_initializer_for__StorportSignals__`
- size: `2271`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18000d3e0`
- `0x18001f634`

## string_xrefs

- `0x18000662c`: `SrbStatusCommandTimeout`
- `0x1800066f9`: `SenseKeyNotReady`
- `0x1800067ef`: `SenseKeyAbortedCommand`
- `0x180006841`: `MediumErrorUnrecoveredRead`
- `0x180006937`: `HardwareErrorDefectListUpdateFailure`
- `0x1800068bc`: `MediumErrorDefectListUpdateFailure`
- `0x1800069db`: `HardwareErrorDataPathFailure`
- `0x1800069b2`: `HardwareErrorLogicalUnitErrorFailedUpdate`
- `0x180006a7f`: `HardwareErrorFailedSelfConfiguration`
- `0x180006bc7`: `WriteIOCount`
- `0x180006b9e`: `ReadIOCount`

## pseudocode

```c
// Hidden C++ exception states: #wind=107
int StorageHealth::_dynamic_initializer_for__StorportSignals__()
{
  std::wstring::wstring((__int64)qword_1800C1250, (__int64)L"VendorId");
  std::wstring::wstring((__int64)qword_1800C1270, (__int64)L"StorportErrPerf");
  dword_1800C1290 = 3;
  std::wstring::wstring((__int64)qword_1800C1298, (__int64)L"MiniportName");
  std::wstring::wstring((__int64)qword_1800C12B8, (__int64)L"StorportErrPerf");
  dword_1800C12D8 = 3;
  std::wstring::wstring((__int64)qword_1800C12E0, (__int64)L"SrbStatusAborted");
  std::wstring::wstring((__int64)qword_1800C1300, (__int64)L"StorportErrPerf");
  dword_1800C1320 = 0;
  std::wstring::wstring((__int64)qword_1800C1328, (__int64)L"SrbStatusError");
  std::wstring::wstring((__int64)qword_1800C1348, (__int64)L"StorportErrPerf");
  dword_1800C1368 = 0;
  std::wstring::wstring((__int64)qword_1800C1370, (__int64)L"SrbStatusBusy");
  std::wstring::wstring((__int64)qword_1800C1390, (__int64)L"StorportErrPerf");
  dword_1800C13B0 = 0;
  std::wstring::wstring((__int64)qword_1800C13B8, (__int64)L"SrbStatusInvalidRequest");
  std::wstring::wstring((__int64)qword_1800C13D8, (__int64)L"StorportErrPerf");
  dword_1800C13F8 = 0;
  std::wstring::wstring((__int64)qword_1800C1400, (__int64)L"SrbStatusNoDevice");
  std::wstring::wstring((__int64)qword_1800C1420, (__int64)L"StorportErrPerf");
  dword_1800C1440 = 0;
  std::wstring::wstring((__int64)qword_1800C1448, (__int64)L"SrbStatusTimeout");
  std::wstring::wstring((__int64)qword_1800C1468, (__int64)L"StorportErrPerf");
  dword_1800C1488 = 0;
  std::wstring::wstring((__int64)qword_1800C1490, (__int64)L"SrbStatusSelectionTimeout");
  std::wstring::wstring((__int64)qword_1800C14B0, (__int64)L"StorportErrPerf");
  dword_1800C14D0 = 0;
  std::wstring::wstring((__int64)qword_1800C14D8, (__int64)L"SrbStatusCommandTimeout");
  std::wstring::wstring((__int64)qword_1800C14F8, (__int64)L"StorportErrPerf");
  dword_1800C1518 = 0;
  std::wstring::wstring((__int64)qword_1800C1520, (__int64)L"SrbStatusBusReset");
  std::wstring::wstring((__int64)qword_1800C1540, (__int64)L"StorportErrPerf");
  dword_1800C1560 = 0;
  std::wstring::wstring((__int64)qword_1800C1568, (__int64)L"SrbStatusParityError");
  std::wstring::wstring((__int64)qword_1800C1588, (__int64)L"StorportErrPerf");
  dword_1800C15A8 = 0;
  std::wstring::wstring((__int64)qword_1800C15B0, (__int64)L"SrbStatusNoHba");
  std::wstring::wstring((__int64)qword_1800C15D0, (__int64)L"StorportErrPerf");
  dword_1800C15F0 = 0;
  std::wstring::wstring((__int64)qword_1800C15F8, (__int64)L"SenseKeyRecoveredError");
  std::wstring::wstring((__int64)qword_1800C1618, (__int64)L"StorportErrPerf");
  dword_1800C1638 = 0;
  std::wstring::wstring((__int64)qword_1800C1640, (__int64)L"SenseKeyNotReady");
  std::wstring::wstring((__int64)qword_1800C1660, (__int64)L"StorportErrPerf");
  dword_1800C1680 = 0;
  std::wstring::wstring((__int64)qword_1800C1688, (__int64)L"SenseKeyMediumError");
  std::wstring::wstring((__int64)qword_1800C16A8, (__int64)L"StorportErrPerf");
  dword_1800C16C8 = 0;
  std::wstring::wstring((__int64)qword_1800C16D0, (__int64)L"SenseKeyHardwareError");
  std::wstring::wstring((__int64)qword_1800C16F0, (__int64)L"StorportErrPerf");
  dword_1800C1710 = 0;
  std::wstring::wstring((__int64)qword_1800C1718, (__int64)L"SenseKeyIllegalRequest");
  std::wstring::wstring((__int64)qword_1800C1738, (__int64)L"StorportErrPerf");
  dword_1800C1758 = 0;
  std::wstring::wstring((__int64)qword_1800C1760, (__int64)L"SenseKeyUnitAttention");
  std::wstring::wstring((__int64)qword_1800C1780, (__int64)L"StorportErrPerf");
  dword_1800C17A0 = 0;
  std::wstring::wstring((__int64)qword_1800C17A8, (__int64)L"SenseKeyDataProtect");
  std::wstring::wstring((__int64)qword_1800C17C8, (__int64)L"StorportErrPerf");
  dword_1800C17E8 = 0;
  std::wstring::wstring((__int64)qword_1800C17F0, (__int64)L"SenseKeyAbortedCommand");
  std::wstring::wstring((__int64)qword_1800C1810, (__int64)L"StorportErrPerf");
  dword_1800C1830 = 0;
  std::wstring::wstring((__int64)qword_1800C1838, (__int64)L"MediumErrorCRC");
  std::wstring::wstring((__int64)qword_1800C1858, (__int64)L"StorportErrPerf");
  dword_1800C1878 = 0;
  std::wstring::wstring((__int64)qword_1800C1880, (__int64)L"MediumErrorUnrecoveredRead");
  std::wstring::wstring((__int64)qword_1800C18A0, (__int64)L"StorportErrPerf");
  dword_1800C18C0 = 0;
  std::wstring::wstring((__int64)qword_1800C18C8, (__int64)L"MediumErrorDefectList");
  std::wstring::wstring((__int64)qword_1800C18E8, (__int64)L"StorportErrPerf");
  dword_1800C1908 = 0;
  std::wstring::wstring((__int64)qword_1800C1910, (__int64)L"MediumErrorDefectListNoSpare");
  std::wstring::wstring((__int64)qword_1800C1930, (__int64)L"StorportErrPerf");
  dword_1800C1950 = 0;
  std::wstring::wstring((__int64)qword_1800C1958, (__int64)L"MediumErrorDefectListUpdateFailure");
  std::wstring::wstring((__int64)qword_1800C1978, (__int64)L"StorportErrPerf");
  dword_1800C1998 = 0;
  std::wstring::wstring((__int64)qword_1800C19A0, (__int64)L"HardwareErrorDefectList");
  std::wstring::wstring((__int64)qword_1800C19C0, (__int64)L"StorportErrPerf");
  dword_1800C19E0 = 0;
  std::wstring::wstring((__int64)qword_1800C19E8, (__int64)L"HardwareErrorDefectListNoSpare");
  std::wstring::wstring((__int64)qword_1800C1A08, (__int64)L"StorportErrPerf");
  dword_1800C1A28 = 0;
  std::wstring::wstring((__int64)qword_1800C1A30, (__int64)L"HardwareErrorDefectListUpdateFailure");
  std::wstring::wstring((__int64)qword_1800C1A50, (__int64)L"StorportErrPerf");
  dword_1800C1A70 = 0;
  std::wstring::wstring((__int64)qword_1800C1A78, (__int64)L"HardwareErrorLogicalUnitError");
  std::wstring::wstring((__int64)qword_1800C1A98, (__int64)L"StorportErrPerf");
  dword_1800C1AB8 = 0;
  std::wstring::wstring((__int64)qword_1800C1AC0, (__int64)L"HardwareErrorLogicalUnitErrorFailedSelf");
  std::wstring::wstring((__int64)qword_1800C1AE0, (__int64)L"StorportErrPerf");
  dword_1800C1B00 = 0;
  std::wstring::wstring((__int64)qword_1800C1B08, (__int64)L"HardwareErrorLogicalUnitErrorFailedUpdate");
  std::wstring::wstring((__int64)qword_1800C1B28, (__int64)L"StorportErrPerf");
  dword_1800C1B48 = 0;
  std::wstring::wstring((__int64)qword_1800C1B50, (__int64)L"HardwareErrorDataPathFailure");
  std::wstring::wstring((__int64)qword_1800C1B70, (__int64)L"StorportErrPerf");
  dword_1800C1B90 = 0;
  std::wstring::wstring((__int64)qword_1800C1B98, (__int64)L"HardwareErrorPowerOnSelfTestFailure");
  std::wstring::wstring((__int64)qword_1800C1BB8, (__int64)L"StorportErrPerf");
  dword_1800C1BD8 = 0;
  std::wstring::wstring((__int64)qword_1800C1BE0, (__int64)L"HardwareErrorInternalTargetFailure");
  std::wstring::wstring((__int64)qword_1800C1C00, (__int64)L"StorportErrPerf");
  dword_1800C1C20 = 0;
  std::wstring::wstring((__int64)qword_1800C1C28, (__int64)L"HardwareErrorInternalTargetFailureInternal");
  std::wstring::wstring((__int64)qword_1800C1C48, (__int64)L"StorportErrPerf");
  dword_1800C1C68 = 0;
  std::wstring::wstring((__int64)qword_1800C1C70, (__int64)L"HardwareErrorFailedSelfConfiguration");
  std::wstring::wstring((__int64)qword_1800C1C90, (__int64)L"StorportErrPerf");
  dword_1800C1CB0 = 0;
  std::wstring::wstring((__int64)qword_1800C1CB8, (__int64)L"HardwareErrorResourceFailure");
  std::wstring::wstring((__int64)qword_1800C1CD8, (__int64)L"StorportErrPerf");
  dword_1800C1CF8 = 0;
  std::wstring::wstring((__int64)qword_1800C1D00, (__int64)L"HardwareErrorResourceFailureFailure");
  std::wstring::wstring((__int64)qword_1800C1D20, (__int64)L"StorportErrPerf");
  dword_1800C1D40 = 0;
  std::wstring::wstring((__int64)qword_1800C1D48, (__int64)L"StRtlTotalDeviceFailure");
  std::wstring::wstring((__int64)qword_1800C1D68, (__int64)L"StorportErrPerf");
  dword_1800C1D88 = 0;
  std::wstring::wstring((__int64)qword_1800C1D90, (__int64)L"ErrorHours");
  std::wstring::wstring((__int64)qword_1800C1DB0, (__int64)L"StorportErrPerf");
  dword_1800C1DD0 = 0;
  std::wstring::wstring((__int64)qword_1800C1DD8, (__int64)L"PerfHours");
  std::wstring::wstring((__int64)qword_1800C1DF8, (__int64)L"StorportErrPerf");
  dword_1800C1E18 = 0;
  std::wstring::wstring((__int64)qword_1800C1E20, (__int64)L"IOCount");
  std::wstring::wstring((__int64)qword_1800C1E40, (__int64)L"StorportErrPerf");
  dword_1800C1E60 = 0;
  std::wstring::wstring((__int64)qword_1800C1E68, (__int64)L"ReadIOCount");
  std::wstring::wstring((__int64)qword_1800C1E88, (__int64)L"StorportErrPerf");
  dword_1800C1EA8 = 0;
  std::wstring::wstring((__int64)qword_1800C1EB0, (__int64)L"WriteIOCount");
  std::wstring::wstring((__int64)qword_1800C1ED0, (__int64)L"StorportErrPerf");
  dword_1800C1EF0 = 0;
  std::wstring::wstring((__int64)qword_1800C1EF8, (__int64)L"AverageMaxIOLatency");
  std::wstring::wstring((__int64)qword_1800C1F18, (__int64)L"StorportErrPerf");
  dword_1800C1F38 = 2;
  std::wstring::wstring((__int64)qword_1800C1F40, (__int64)L"PeakIOCount");
  std::wstring::wstring((__int64)qword_1800C1F60, (__int64)L"StorportErrPerf");
  dword_1800C1F80 = 0;
  std::wstring::wstring((__int64)qword_1800C1F88, (__int64)L"PerfPercent");
  std::wstring::wstring((__int64)qword_1800C1FA8, (__int64)L"StorportErrPerf");
  dword_1800C1FC8 = 0;
  std::wstring::wstring((__int64)qword_1800C1FD0, (__int64)L"BucketIOLatency");
  std::wstring::wstring((__int64)qword_1800C1FF0, (__int64)L"StorportErrPerf");
  dword_1800C2010 = 3;
  std::wstring::wstring((__int64)qword_1800C2018, (__int64)L"BucketIOCount0");
  std::wstring::wstring((__int64)qword_1800C2038, (__int64)L"StorportErrPerf");
  dword_1800C2058 = 0;
  std::wstring::wstring((__int64)qword_1800C2060, (__int64)L"BucketIOCount1");
  std::wstring::wstring((__int64)qword_1800C2080, (__int64)L"StorportErrPerf");
  dword_1800C20A0 = 0;
  std::wstring::wstring((__int64)qword_1800C20A8, (__int64)L"BucketIOCount2");
  std::wstring::wstring((__int64)qword_1800C20C8, (__int64)L"StorportErrPerf");
  dword_1800C20E8 = 0;
  std::wstring::wstring((__int64)qword_1800C20F0, (__int64)L"BucketIOCount3");
  std::wstring::wstring((__int64)qword_1800C2110, (__int64)L"StorportErrPerf");
  dword_1800C2130 = 0;
  std::wstring::wstring((__int64)qword_1800C2138, (__int64)L"BucketIOCount4");
  std::wstring::wstring((__int64)qword_1800C2158, (__int64)L"StorportErrPerf");
  dword_1800C2178 = 0;
  return atexit((void (__cdecl *)())StorageHealth::_dynamic_atexit_destructor_for__StorportSignals__);
}

```

## disassembly

```asm
0x1800064a0  mov     [rsp+arg_0], rsi
0x1800064a5  push    rdi
0x1800064a6  sub     rsp, 20h
0x1800064aa  lea     rdx, aVendorid; "VendorId"
0x1800064b1  lea     rcx, qword_1800C1250
0x1800064b8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800064bd  nop
0x1800064be  lea     rsi, aStorporterrper; "StorportErrPerf"
0x1800064c5  mov     rdx, rsi
0x1800064c8  lea     rcx, qword_1800C1270
0x1800064cf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800064d4  mov     cs:dword_1800C1290, 3
0x1800064de  lea     rdx, aMiniportname; "MiniportName"
0x1800064e5  lea     rcx, qword_1800C1298
0x1800064ec  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800064f1  nop
0x1800064f2  mov     rdx, rsi
0x1800064f5  lea     rcx, qword_1800C12B8
0x1800064fc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180006501  mov     cs:dword_1800C12D8, 3
0x18000650b  lea     rdx, aSrbstatusabort_19; "SrbStatusAborted"
0x180006512  lea     rcx, qword_1800C12E0
0x180006519  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000651e  nop
0x18000651f  mov     rdx, rsi
0x180006522  lea     rcx, qword_1800C1300
0x180006529  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000652e  xor     edi, edi
0x180006530  mov     cs:dword_1800C1320, edi
0x180006536  lea     rdx, aSrbstatuserror; "SrbStatusError"
0x18000653d  lea     rcx, qword_1800C1328
0x180006544  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180006549  nop
0x18000654a  mov     rdx, rsi
0x18000654d  lea     rcx, qword_1800C1348
0x180006554  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180006559  mov     cs:dword_1800C1368, edi
0x18000655f  lea     rdx, aSrbstatusbusy; "SrbStatusBusy"
0x180006566  lea     rcx, qword_1800C1370
0x18000656d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180006572  nop
0x180006573  mov     rdx, rsi
0x180006576  lea     rcx, qword_1800C1390
0x18000657d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180006582  mov     cs:dword_1800C13B0, edi
0x180006588  lea     rdx, aSrbstatusinval_5; "SrbStatusInvalidRequest"
0x18000658f  lea     rcx, qword_1800C13B8
0x180006596  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000659b  nop
0x18000659c  mov     rdx, rsi
0x18000659f  lea     rcx, qword_1800C13D8
0x1800065a6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800065ab  mov     cs:dword_1800C13F8, edi
0x1800065b1  lea     rdx, aSrbstatusnodev_7; "SrbStatusNoDevice"
0x1800065b8  lea     rcx, qword_1800C1400
0x1800065bf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800065c4  nop
0x1800065c5  mov     rdx, rsi
0x1800065c8  lea     rcx, qword_1800C1420
0x1800065cf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800065d4  mov     cs:dword_1800C1440, edi
0x1800065da  lea     rdx, aSrbstatustimeo_8; "SrbStatusTimeout"
0x1800065e1  lea     rcx, qword_1800C1448
0x1800065e8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800065ed  nop
0x1800065ee  mov     rdx, rsi
0x1800065f1  lea     rcx, qword_1800C1468
0x1800065f8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800065fd  mov     cs:dword_1800C1488, edi
0x180006603  lea     rdx, aSrbstatusselec_6; "SrbStatusSelectionTimeout"
0x18000660a  lea     rcx, qword_1800C1490
0x180006611  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180006616  nop
0x180006617  mov     rdx, rsi
0x18000661a  lea     rcx, qword_1800C14B0
0x180006621  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180006626  mov     cs:dword_1800C14D0, edi
0x18000662c  lea     rdx, aSrbstatuscomma_2; "SrbStatusCommandTimeout"
0x180006633  lea     rcx, qword_1800C14D8
0x18000663a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000663f  nop
0x180006640  mov     rdx, rsi
0x180006643  lea     rcx, qword_1800C14F8
0x18000664a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000664f  mov     cs:dword_1800C1518, edi
0x180006655  lea     rdx, aSrbstatusbusre_3; "SrbStatusBusReset"
0x18000665c  lea     rcx, qword_1800C1520
0x180006663  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180006668  nop
0x180006669  mov     rdx, rsi
0x18000666c  lea     rcx, qword_1800C1540
0x180006673  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180006678  mov     cs:dword_1800C1560, edi
0x18000667e  lea     rdx, aSrbstatusparit_5; "SrbStatusParityError"
0x180006685  lea     rcx, qword_1800C1568
0x18000668c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180006691  nop
0x180006692  mov     rdx, rsi
0x180006695  lea     rcx, qword_1800C1588
0x18000669c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800066a1  mov     cs:dword_1800C15A8, edi
0x1800066a7  lea     rdx, aSrbstatusnohba_5; "SrbStatusNoHba"
0x1800066ae  lea     rcx, qword_1800C15B0
0x1800066b5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800066ba  nop
0x1800066bb  mov     rdx, rsi
0x1800066be  lea     rcx, qword_1800C15D0
0x1800066c5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800066ca  mov     cs:dword_1800C15F0, edi
0x1800066d0  lea     rdx, aSensekeyrecove; "SenseKeyRecoveredError"
0x1800066d7  lea     rcx, qword_1800C15F8
0x1800066de  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800066e3  nop
0x1800066e4  mov     rdx, rsi
0x1800066e7  lea     rcx, qword_1800C1618
0x1800066ee  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800066f3  mov     cs:dword_1800C1638, edi
0x1800066f9  lea     rdx, aSensekeynotrea; "SenseKeyNotReady"
0x180006700  lea     rcx, qword_1800C1640
0x180006707  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000670c  nop
0x18000670d  mov     rdx, rsi
0x180006710  lea     rcx, qword_1800C1660
0x180006717  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000671c  mov     cs:dword_1800C1680, edi
0x180006722  lea     rdx, aSensekeymedium; "SenseKeyMediumError"
0x180006729  lea     rcx, qword_1800C1688
0x180006730  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180006735  nop
0x180006736  mov     rdx, rsi
0x180006739  lea     rcx, qword_1800C16A8
0x180006740  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180006745  mov     cs:dword_1800C16C8, edi
0x18000674b  lea     rdx, aSensekeyhardwa; "SenseKeyHardwareError"
0x180006752  lea     rcx, qword_1800C16D0
0x180006759  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000675e  nop
0x18000675f  mov     rdx, rsi
0x180006762  lea     rcx, qword_1800C16F0
0x180006769  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000676e  mov     cs:dword_1800C1710, edi
0x180006774  lea     rdx, aSensekeyillega; "SenseKeyIllegalRequest"
0x18000677b  lea     rcx, qword_1800C1718
0x180006782  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180006787  nop
0x180006788  mov     rdx, rsi
0x18000678b  lea     rcx, qword_1800C1738
0x180006792  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180006797  mov     cs:dword_1800C1758, edi
0x18000679d  lea     rdx, aSensekeyunitat; "SenseKeyUnitAttention"
0x1800067a4  lea     rcx, qword_1800C1760
0x1800067ab  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800067b0  nop
0x1800067b1  mov     rdx, rsi
0x1800067b4  lea     rcx, qword_1800C1780
0x1800067bb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800067c0  mov     cs:dword_1800C17A0, edi
0x1800067c6  lea     rdx, aSensekeydatapr; "SenseKeyDataProtect"
0x1800067cd  lea     rcx, qword_1800C17A8
0x1800067d4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800067d9  nop
0x1800067da  mov     rdx, rsi
0x1800067dd  lea     rcx, qword_1800C17C8
0x1800067e4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800067e9  mov     cs:dword_1800C17E8, edi
0x1800067ef  lea     rdx, aSensekeyaborte; "SenseKeyAbortedCommand"
0x1800067f6  lea     rcx, qword_1800C17F0
0x1800067fd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180006802  nop
0x180006803  mov     rdx, rsi
0x180006806  lea     rcx, qword_1800C1810
0x18000680d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180006812  mov     cs:dword_1800C1830, edi
0x180006818  lea     rdx, aMediumerrorcrc_3; "MediumErrorCRC"
0x18000681f  lea     rcx, qword_1800C1838
0x180006826  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000682b  nop
0x18000682c  mov     rdx, rsi
0x18000682f  lea     rcx, qword_1800C1858
0x180006836  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000683b  mov     cs:dword_1800C1878, edi
0x180006841  lea     rdx, aMediumerrorunr_2; "MediumErrorUnrecoveredRead"
0x180006848  lea     rcx, qword_1800C1880
0x18000684f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180006854  nop
0x180006855  mov     rdx, rsi
0x180006858  lea     rcx, qword_1800C18A0
0x18000685f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180006864  mov     cs:dword_1800C18C0, edi
0x18000686a  lea     rdx, aMediumerrordef_19; "MediumErrorDefectList"
0x180006871  lea     rcx, qword_1800C18C8
0x180006878  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000687d  nop
0x18000687e  mov     rdx, rsi
0x180006881  lea     rcx, qword_1800C18E8
0x180006888  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000688d  mov     cs:dword_1800C1908, edi
0x180006893  lea     rdx, aMediumerrordef_0; "MediumErrorDefectListNoSpare"
0x18000689a  lea     rcx, qword_1800C1910
0x1800068a1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800068a6  nop
0x1800068a7  mov     rdx, rsi
0x1800068aa  lea     rcx, qword_1800C1930
0x1800068b1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800068b6  mov     cs:dword_1800C1950, edi
0x1800068bc  lea     rdx, aMediumerrordef_1; "MediumErrorDefectListUpdateFailure"
0x1800068c3  lea     rcx, qword_1800C1958
0x1800068ca  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800068cf  nop
0x1800068d0  mov     rdx, rsi
0x1800068d3  lea     rcx, qword_1800C1978
0x1800068da  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800068df  mov     cs:dword_1800C1998, edi
0x1800068e5  lea     rdx, aHardwareerrord; "HardwareErrorDefectList"
0x1800068ec  lea     rcx, qword_1800C19A0
0x1800068f3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800068f8  nop
0x1800068f9  mov     rdx, rsi
0x1800068fc  lea     rcx, qword_1800C19C0
0x180006903  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180006908  mov     cs:dword_1800C19E0, edi
0x18000690e  lea     rdx, aHardwareerrord_1; "HardwareErrorDefectListNoSpare"
0x180006915  lea     rcx, qword_1800C19E8
0x18000691c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180006921  nop
0x180006922  mov     rdx, rsi
0x180006925  lea     rcx, qword_1800C1A08
0x18000692c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180006931  mov     cs:dword_1800C1A28, edi
0x180006937  lea     rdx, aHardwareerrord_0; "HardwareErrorDefectListUpdateFailure"
0x18000693e  lea     rcx, qword_1800C1A30
0x180006945  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000694a  nop
0x18000694b  mov     rdx, rsi
0x18000694e  lea     rcx, qword_1800C1A50
0x180006955  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000695a  mov     cs:dword_1800C1A70, edi
0x180006960  lea     rdx, aHardwareerrorl; "HardwareErrorLogicalUnitError"
0x180006967  lea     rcx, qword_1800C1A78
0x18000696e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180006973  nop
0x180006974  mov     rdx, rsi
0x180006977  lea     rcx, qword_1800C1A98
0x18000697e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180006983  mov     cs:dword_1800C1AB8, edi
0x180006989  lea     rdx, aHardwareerrorl_1; "HardwareErrorLogicalUnitErrorFailedSelf"
0x180006990  lea     rcx, qword_1800C1AC0
0x180006997  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000699c  nop
0x18000699d  mov     rdx, rsi
0x1800069a0  lea     rcx, qword_1800C1AE0
0x1800069a7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800069ac  mov     cs:dword_1800C1B00, edi
0x1800069b2  lea     rdx, aHardwareerrorl_0; "HardwareErrorLogicalUnitErrorFailedUpda"...
0x1800069b9  lea     rcx, qword_1800C1B08
0x1800069c0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800069c5  nop
0x1800069c6  mov     rdx, rsi
0x1800069c9  lea     rcx, qword_1800C1B28
0x1800069d0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800069d5  mov     cs:dword_1800C1B48, edi
0x1800069db  lea     rdx, aHardwareerrord_2; "HardwareErrorDataPathFailure"
0x1800069e2  lea     rcx, qword_1800C1B50
0x1800069e9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800069ee  nop
0x1800069ef  mov     rdx, rsi
0x1800069f2  lea     rcx, qword_1800C1B70
0x1800069f9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800069fe  mov     cs:dword_1800C1B90, edi
0x180006a04  lea     rdx, aHardwareerrorp; "HardwareErrorPowerOnSelfTestFailure"
0x180006a0b  lea     rcx, qword_1800C1B98
0x180006a12  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180006a17  nop
0x180006a18  mov     rdx, rsi
0x180006a1b  lea     rcx, qword_1800C1BB8
0x180006a22  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180006a27  mov     cs:dword_1800C1BD8, edi
0x180006a2d  lea     rdx, aHardwareerrori; "HardwareErrorInternalTargetFailure"
0x180006a34  lea     rcx, qword_1800C1BE0
0x180006a3b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180006a40  nop
0x180006a41  mov     rdx, rsi
0x180006a44  lea     rcx, qword_1800C1C00
0x180006a4b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180006a50  mov     cs:dword_1800C1C20, edi
0x180006a56  lea     rdx, aHardwareerrori_0; "HardwareErrorInternalTargetFailureInter"...
0x180006a5d  lea     rcx, qword_1800C1C28
0x180006a64  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180006a69  nop
0x180006a6a  mov     rdx, rsi
0x180006a6d  lea     rcx, qword_1800C1C48
0x180006a74  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180006a79  mov     cs:dword_1800C1C68, edi
0x180006a7f  lea     rdx, aHardwareerrorf; "HardwareErrorFailedSelfConfiguration"
0x180006a86  lea     rcx, qword_1800C1C70
0x180006a8d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180006a92  nop
0x180006a93  mov     rdx, rsi
0x180006a96  lea     rcx, qword_1800C1C90
0x180006a9d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
  ... truncated ...
```
