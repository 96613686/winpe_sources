# WorkerModule::InitializeSelf(void)

- ea: `0x14013d6ac`
- end: `0x14013e0bf`
- name: `?InitializeSelf@WorkerModule@@QEAAXXZ`
- size: `2579`
- prototype: `void __fastcall(WorkerModule *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400c3818`

## callees

- `0x140042240`
- `0x14004c13c`
- `0x14004ef04`
- `0x140054af0`
- `0x14005b628`
- `0x140132940`
- `0x1401335fc`
- `0x14013b6a0`
- `0x14013b748`
- `0x14013d6ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14013e046`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14013e046`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14013e09a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14013e09a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14013dfca`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14013dfca`

## string_xrefs

- `0x14013e052`: `Cannot create initialization timeout timer. Error code: %d.\n`

## pseudocode

```c
void __fastcall WorkerModule::InitializeSelf(WorkerModule *this)
{
  const struct wil::FailureInfo *v1; // rdx
  const char *v2; // r9
  DWORD LastError; // eax
  _BYTE v4[160]; // [rsp+20h] [rbp-B8h] BYREF
  struct _FILETIME pftDueTime; // [rsp+C0h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  qword_1403B8170 = (__int64)MSVML_WORKER_EXCEPTIONS_INFO;
  qword_1403BBD50 = (__int64)MSVM_WORKER_MIGRATION_DEBUG_INFO;
  qword_1403B8168 = (__int64)MSVML_WORKER_EXCEPTIONS_WARNING;
  qword_1403BBD48 = (__int64)MSVM_WORKER_MIGRATION_DEBUG_WARNING;
  qword_1403B8160 = (__int64)MSVML_WORKER_EXCEPTIONS_ERROR;
  qword_1403BBD40 = (__int64)MSVM_WORKER_MIGRATION_DEBUG_ERROR;
  qword_1403B8158 = (__int64)MSVML_WORKER_EXCEPTIONS_CRITICAL;
  qword_1403B8190 = (__int64)MSVML_WORKER_MODULES_INFO;
  qword_1403B8188 = (__int64)MSVML_WORKER_MODULES_WARNING;
  qword_1403B8180 = (__int64)MSVML_WORKER_MODULES_ERROR;
  qword_1403B8178 = (__int64)MSVML_WORKER_MODULES_CRITICAL;
  qword_1403B81B0 = (__int64)MSVML_WORKER_COM_INFO;
  qword_1403B81A8 = (__int64)MSVML_WORKER_COM_WARNING;
  qword_1403B81A0 = (__int64)MSVML_WORKER_COM_ERROR;
  qword_1403B8198 = (__int64)MSVML_WORKER_COM_CRITICAL;
  qword_1403B81D0 = (__int64)MSVML_WORKER_REGISTRY_INFO;
  qword_1403B81C8 = (__int64)MSVML_WORKER_REGISTRY_WARNING;
  qword_1403B81C0 = (__int64)MSVML_WORKER_REGISTRY_ERROR;
  qword_1403B81B8 = (__int64)MSVML_WORKER_REGISTRY_CRITICAL;
  qword_1403B81F0 = (__int64)MSVML_WORKER_THREADS_INFO;
  qword_1403B81E8 = (__int64)MSVML_WORKER_THREADS_WARNING;
  qword_1403B81E0 = (__int64)MSVML_WORKER_THREADS_ERROR;
  qword_1403B81D8 = (__int64)MSVML_WORKER_THREADS_CRITICAL;
  qword_1403B8210 = (__int64)MSVML_WORKER_REFCOUNTED_INFO;
  qword_1403B8208 = (__int64)MSVML_WORKER_REFCOUNTED_WARNING;
  qword_1403B8200 = (__int64)MSVML_WORKER_REFCOUNTED_ERROR;
  qword_1403B81F8 = (__int64)MSVML_WORKER_REFCOUNTED_CRITICAL;
  qword_1403B8230 = (__int64)MSVML_WORKER_WMI_INFO;
  qword_1403B8228 = (__int64)MSVML_WORKER_WMI_WARNING;
  qword_1403B8220 = (__int64)MSVML_WORKER_WMI_ERROR;
  qword_1403B8218 = (__int64)MSVML_WORKER_WMI_CRITICAL;
  qword_1403BBD38 = (__int64)MSVM_WORKER_MIGRATION_DEBUG_CRITICAL;
  qword_1403BBD78 = (__int64)MSVM_WORKER_MIGRATION_DEBUG_CRITICAL;
  qword_1403B9950 = (__int64)MSVDEV_BIOS_INFO;
  qword_1403B9948 = (__int64)MSVDEV_BIOS_WARNING;
  qword_1403B9940 = (__int64)MSVDEV_BIOS_ERROR;
  qword_1403B9938 = (__int64)MSVDEV_BIOS_CRITICAL;
  qword_1403B9970 = (__int64)MSVDEV_CMOS_INFO;
  qword_1403B9968 = (__int64)MSVDEV_CMOS_WARNING;
  qword_1403BBD90 = (__int64)MSVM_WORKER_MIGRATION_DEBUG_INFO;
  qword_1403BBD88 = (__int64)MSVM_WORKER_MIGRATION_DEBUG_WARNING;
  qword_1403BBD80 = (__int64)MSVM_WORKER_MIGRATION_DEBUG_ERROR;
  qword_1403B9960 = (__int64)MSVDEV_CMOS_ERROR;
  qword_1403B9958 = (__int64)MSVDEV_CMOS_CRITICAL;
  qword_1403B9990 = (__int64)MSVDEV_POWER_MANAGEMENT_INFO;
  qword_1403B9988 = (__int64)MSVDEV_POWER_MANAGEMENT_WARNING;
  qword_1403B9980 = (__int64)MSVDEV_POWER_MANAGEMENT_ERROR;
  qword_1403B9978 = (__int64)MSVDEV_POWER_MANAGEMENT_CRITICAL;
  qword_1403B99B0 = (__int64)MSVDEV_SM_BUS_INFO;
  qword_1403B99A8 = (__int64)MSVDEV_SM_BUS_WARNING;
  qword_1403B99A0 = (__int64)MSVDEV_SM_BUS_ERROR;
  qword_1403B9998 = (__int64)MSVDEV_SM_BUS_CRITICAL;
  qword_1403B99D0 = (__int64)MSVDEV_ISA_BUS_INFO;
  qword_1403B99C8 = (__int64)MSVDEV_ISA_BUS_WARNING;
  qword_1403B99C0 = (__int64)MSVDEV_ISA_BUS_ERROR;
  qword_1403B99B8 = (__int64)MSVDEV_ISA_BUS_CRITICAL;
  qword_1403B99F0 = (__int64)MSVDEV_PCI_BUS_INFO;
  qword_1403B99E8 = (__int64)MSVDEV_PCI_BUS_WARNING;
  qword_1403B99E0 = (__int64)MSVDEV_PCI_BUS_ERROR;
  qword_1403B99D8 = (__int64)"2(";
  qword_1403B9A10 = (__int64)MSVDEV_APIC_INFO;
  qword_1403B9A08 = (__int64)MSVDEV_APIC_WARNING;
  qword_1403B9A00 = (__int64)MSVDEV_APIC_ERROR;
  qword_1403B99F8 = (__int64)MSVDEV_APIC_CRITICAL;
  qword_1403B9A30 = (__int64)MSVDEV_DMA_INFO;
  qword_1403B9A28 = (__int64)MSVDEV_DMA_WARNING;
  qword_1403B9A20 = (__int64)MSVDEV_DMA_ERROR;
  qword_1403B9A18 = (__int64)MSVDEV_DMA_CRITICAL;
  qword_1403B9A50 = (__int64)MSVDEV_PIC_INFO;
  qword_1403B9A48 = (__int64)MSVDEV_PIC_WARNING;
  qword_1403B9A40 = (__int64)MSVDEV_PIC_ERROR;
  qword_1403B9A38 = (__int64)MSVDEV_PIC_CRITICAL;
  qword_1403B9A70 = (__int64)MSVDEV_PIT_INFO;
  qword_1403B9A68 = (__int64)MSVDEV_PIT_WARNING;
  qword_1403B9A60 = (__int64)MSVDEV_PIT_ERROR;
  qword_1403B9A58 = (__int64)MSVDEV_PIT_CRITICAL;
  qword_1403B9A90 = (__int64)MSVDEV_SUPER_IO_INFO;
  qword_1403B9A88 = (__int64)MSVDEV_SUPER_IO_WARNING;
  qword_1403B9A80 = (__int64)MSVDEV_SUPER_IO_ERROR;
  qword_1403B9A78 = (__int64)MSVDEV_SUPER_IO_CRITICAL;
  qword_1403B9AB0 = (__int64)MSVDEV_SERIAL_CONTROLLER_INFO;
  qword_1403B9AA8 = (__int64)MSVDEV_SERIAL_CONTROLLER_WARNING;
  qword_1403B9AA0 = (__int64)MSVDEV_SERIAL_CONTROLLER_ERROR;
  qword_1403B9A98 = (__int64)MSVDEV_SERIAL_CONTROLLER_CRITICAL;
  qword_1403B9AF0 = (__int64)"|)";
  qword_1403B9AD0 = (__int64)MSVDEV_KEYBOARD_INFO;
  qword_1403B9AE8 = (__int64)MSVDEV_MOUSE_WARNING;
  qword_1403B9AC8 = (__int64)MSVDEV_KEYBOARD_WARNING;
  qword_1403B9AE0 = (__int64)MSVDEV_MOUSE_ERROR;
  qword_1403B9AC0 = (__int64)MSVDEV_KEYBOARD_ERROR;
  qword_1403B9AB8 = (__int64)MSVDEV_KEYBOARD_CRITICAL;
  qword_1403B9AD8 = (__int64)MSVDEV_MOUSE_CRITICAL;
  qword_1403B9CD8 = (__int64)MSVDEV_MOUSE_CRITICAL;
  qword_1403B9B10 = (__int64)MSVDEV_FLOPPY_CONTROLLER_INFO;
  qword_1403B9B08 = (__int64)MSVDEV_FLOPPY_CONTROLLER_WARNING;
  qword_1403B9B00 = (__int64)MSVDEV_FLOPPY_CONTROLLER_ERROR;
  qword_1403B9AF8 = (__int64)MSVDEV_FLOPPY_CONTROLLER_CRITICAL;
  qword_1403B9B30 = (__int64)MSVDEV_FLOPPY_DRIVE_INFO;
  qword_1403B9B28 = (__int64)MSVDEV_FLOPPY_DRIVE_WARNING;
  qword_1403B9B20 = (__int64)MSVDEV_FLOPPY_DRIVE_ERROR;
  qword_1403B9B18 = (__int64)MSVDEV_FLOPPY_DRIVE_CRITICAL;
  qword_1403B9B50 = (__int64)MSVDEV_IDE_CONTROLLER_INFO;
  qword_1403B9B48 = (__int64)MSVDEV_IDE_CONTROLLER_WARNING;
  qword_1403B9B40 = (__int64)MSVDEV_IDE_CONTROLLER_ERROR;
  qword_1403B9B38 = (__int64)MSVDEV_IDE_CONTROLLER_CRITICAL;
  qword_1403B9B70 = (__int64)MSVDEV_IDE_ATTACHMENT_INFO;
  qword_1403B9B68 = (__int64)MSVDEV_IDE_ATTACHMENT_WARNING;
  qword_1403B9B60 = (__int64)MSVDEV_IDE_ATTACHMENT_ERROR;
  qword_1403B9B58 = (__int64)MSVDEV_IDE_ATTACHMENT_CRITICAL;
  qword_1403B9B90 = (__int64)MSVDEV_SCSI_CONTROLLER_INFO;
  qword_1403B9B88 = (__int64)MSVDEV_SCSI_CONTROLLER_WARNING;
  qword_1403B9B80 = (__int64)MSVDEV_SCSI_CONTROLLER_ERROR;
  qword_1403B9B78 = (__int64)MSVDEV_SCSI_CONTROLLER_CRITICAL;
  qword_1403B9BB0 = (__int64)MSVDEV_SCSI_BUS_INFO;
  qword_1403B9BA8 = (__int64)MSVDEV_SCSI_BUS_WARNING;
  qword_1403B9BA0 = (__int64)MSVDEV_SCSI_BUS_ERROR;
  qword_1403B9B98 = (__int64)MSVDEV_SCSI_BUS_CRITICAL;
  qword_1403B9BD0 = (__int64)MSVDEV_SCSI_ATTACHMENT_INFO;
  qword_1403B9BC8 = (__int64)MSVDEV_SCSI_ATTACHMENT_WARNING;
  qword_1403B9BC0 = (__int64)MSVDEV_SCSI_ATTACHMENT_ERROR;
  qword_1403B9BB8 = (__int64)MSVDEV_SCSI_ATTACHMENT_CRITICAL;
  qword_1403B9BF0 = (__int64)MSVDEV_MEDIA_INFO;
  qword_1403B9CF0 = (__int64)"|)";
  qword_1403B9CE8 = (__int64)MSVDEV_MOUSE_WARNING;
  qword_1403B9CE0 = (__int64)MSVDEV_MOUSE_ERROR;
  qword_1403B9BE8 = (__int64)MSVDEV_MEDIA_WARNING;
  qword_1403B9C50 = (__int64)MSVDEV_VIDEO_CONTROLLER_INFO;
  qword_1403B9BE0 = (__int64)MSVDEV_MEDIA_ERROR;
  qword_1403B9C48 = (__int64)">+";
  qword_1403B9BD8 = (__int64)MSVDEV_MEDIA_CRITICAL;
  qword_1403B9C40 = (__int64)MSVDEV_VIDEO_CONTROLLER_ERROR;
  qword_1403B9C10 = (__int64)MSVDEV_HARD_DRIVE_INFO;
  qword_1403B9C08 = (__int64)MSVDEV_HARD_DRIVE_WARNING;
  qword_1403B9C00 = (__int64)MSVDEV_HARD_DRIVE_ERROR;
  qword_1403B9BF8 = (__int64)MSVDEV_HARD_DRIVE_CRITICAL;
  qword_1403B9C30 = (__int64)MSVDEV_ETHERNET_INFO;
  qword_1403B9C28 = (__int64)MSVDEV_ETHERNET_WARNING;
  qword_1403B9C20 = (__int64)MSVDEV_ETHERNET_ERROR;
  qword_1403B9C18 = (__int64)MSVDEV_ETHERNET_CRITICAL;
  qword_1403B9C38 = (__int64)"R+";
  qword_1403B9CB8 = (__int64)"R+";
  qword_1403B9C70 = (__int64)MSVDEV_REPOSITORY_INFO;
  qword_1403B9C68 = (__int64)"f+";
  qword_1403B9C60 = (__int64)MSVDEV_REPOSITORY_ERROR;
  qword_1403B9C58 = (__int64)MSVDEV_REPOSITORY_CRITICAL;
  qword_1403B9C90 = (__int64)MSVDEV_REMOTING_INFO;
  qword_1403B9C88 = (__int64)MSVDEV_REMOTING_WARNING;
  qword_1403B9C80 = (__int64)MSVDEV_REMOTING_ERROR;
  qword_1403B9C78 = (__int64)MSVDEV_REMOTING_CRITICAL;
  qword_1403B9CB0 = (__int64)MSVDEV_HID_INFO;
  qword_1403B9CA8 = (__int64)MSVDEV_HID_WARNING;
  qword_1403B9CA0 = (__int64)MSVDEV_HID_ERROR;
  qword_1403B9C98 = (__int64)MSVDEV_HID_CRITICAL;
  qword_1403B9D30 = (__int64)MSVDEV_VIRTUAL_MOTHERBOARD_INFO;
  qword_1403B9D28 = (__int64)"6)";
  qword_1403B9D20 = (__int64)MSVDEV_VIRTUAL_MOTHERBOARD_ERROR;
  qword_1403B9D18 = (__int64)MSVDEV_VIRTUAL_MOTHERBOARD_CRITICAL;
  qword_1403BAD50 = (__int64)MSVDEV_DYNMEM_INFO;
  qword_1403BAD48 = (__int64)MSVDEV_DYNMEM_WARNING;
  qword_1403BAD40 = (__int64)MSVDEV_DYNMEM_ERROR;
  qword_1403BAD38 = (__int64)MSVDEV_DYNMEM_CRITICAL;
  qword_1403BAD70 = (__int64)MSVDEV_SYNTH3DVIDEO_INFO;
  qword_1403BAD68 = (__int64)MSVDEV_SYNTH3DVIDEO_WARNING;
  qword_1403BAD60 = (__int64)MSVDEV_SYNTH3DVIDEO_ERROR;
  qword_1403BAD58 = (__int64)MSVDEV_SYNTH3DVIDEO_CRITICAL;
  qword_1403B9CD0 = (__int64)MSVDEV_VIDEO_CONTROLLER_INFO;
  qword_1403B9CC8 = (__int64)">+";
  qword_1403B9CC0 = (__int64)MSVDEV_VIDEO_CONTROLLER_ERROR;
  std::function<void (unsigned short,unsigned short const *)>::operator=<void (&)(unsigned short,unsigned short const *),0>(g_HvsTraceFunctions);
  std::function<bool (unsigned short)>::operator=<int (&)(unsigned short),0>(qword_1403C0C50);
  pti = CreateThreadpoolTimer(WorkerModule::InitializeTimeoutCallback, &g_Module, 0);
  if ( wil::details::g_pfnTelemetryCallback
    && (void (__fastcall *)(bool, const struct wil::FailureInfo *))wil::details::g_pfnTelemetryCallback != VmWorkerTrace::FallbackTelemetryCallback )
  {
    memset_0(v4, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v4, v1);
  }
  wil::details::g_pfnTelemetryCallback = (__int64)VmWorkerTrace::FallbackTelemetryCallback;
  *(_DWORD *)(wil::details::static_lazy<VmWorkerTrace>::get(
                VmWorkerTrace::FallbackTelemetryCallback,
                _lambda_f90d4020ca5a3ee22356c2a70c24b4bd_::_lambda_invoker_cdecl_)
            + 20) = 2;
  if ( !pti )
  {
    if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
    {
      LastError = GetLastError();
      VmlDebugTrace(16416, L"Cannot create initialization timeout timer. Error code: %d.\n", LastError);
    }
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x413,
      (unsigned int)"onecore\\vm\\worker\\wpexe\\workermodule.cpp",
      v2);
  }
  pftDueTime = (struct _FILETIME)-600000000LL;
  SetThreadpoolTimer(pti, &pftDueTime, 0, 0);
}

```

## disassembly

```asm
0x14013d6ac  sub     rsp, 0D8h
0x14013d6b3  mov     rax, cs:__security_cookie
0x14013d6ba  xor     rax, rsp
0x14013d6bd  mov     [rsp+0D8h+var_10], rax
0x14013d6c5  lea     rax, MSVML_WORKER_EXCEPTIONS_INFO
0x14013d6cc  mov     cs:qword_1403B8170, rax
0x14013d6d3  lea     r8, MSVM_WORKER_MIGRATION_DEBUG_INFO
0x14013d6da  lea     rax, MSVML_WORKER_EXCEPTIONS_WARNING
0x14013d6e1  mov     cs:qword_1403BBD50, r8
0x14013d6e8  mov     cs:qword_1403B8168, rax
0x14013d6ef  lea     rdx, MSVM_WORKER_MIGRATION_DEBUG_WARNING
0x14013d6f6  lea     rax, MSVML_WORKER_EXCEPTIONS_ERROR
0x14013d6fd  mov     cs:qword_1403BBD48, rdx
0x14013d704  mov     cs:qword_1403B8160, rax
0x14013d70b  lea     rcx, MSVM_WORKER_MIGRATION_DEBUG_ERROR
0x14013d712  lea     rax, MSVML_WORKER_EXCEPTIONS_CRITICAL
0x14013d719  mov     cs:qword_1403BBD40, rcx
0x14013d720  mov     cs:qword_1403B8158, rax
0x14013d727  lea     rax, MSVML_WORKER_MODULES_INFO
0x14013d72e  mov     cs:qword_1403B8190, rax
0x14013d735  lea     rax, MSVML_WORKER_MODULES_WARNING
0x14013d73c  mov     cs:qword_1403B8188, rax
0x14013d743  lea     rax, MSVML_WORKER_MODULES_ERROR
0x14013d74a  mov     cs:qword_1403B8180, rax
0x14013d751  lea     rax, MSVML_WORKER_MODULES_CRITICAL
0x14013d758  mov     cs:qword_1403B8178, rax
0x14013d75f  lea     rax, MSVML_WORKER_COM_INFO
0x14013d766  mov     cs:qword_1403B81B0, rax
0x14013d76d  lea     rax, MSVML_WORKER_COM_WARNING
0x14013d774  mov     cs:qword_1403B81A8, rax
0x14013d77b  lea     rax, MSVML_WORKER_COM_ERROR
0x14013d782  mov     cs:qword_1403B81A0, rax
0x14013d789  lea     rax, MSVML_WORKER_COM_CRITICAL
0x14013d790  mov     cs:qword_1403B8198, rax
0x14013d797  lea     rax, MSVML_WORKER_REGISTRY_INFO
0x14013d79e  mov     cs:qword_1403B81D0, rax
0x14013d7a5  lea     rax, MSVML_WORKER_REGISTRY_WARNING
0x14013d7ac  mov     cs:qword_1403B81C8, rax
0x14013d7b3  lea     rax, MSVML_WORKER_REGISTRY_ERROR
0x14013d7ba  mov     cs:qword_1403B81C0, rax
0x14013d7c1  lea     rax, MSVML_WORKER_REGISTRY_CRITICAL
0x14013d7c8  mov     cs:qword_1403B81B8, rax
0x14013d7cf  lea     rax, MSVML_WORKER_THREADS_INFO
0x14013d7d6  mov     cs:qword_1403B81F0, rax
0x14013d7dd  lea     rax, MSVML_WORKER_THREADS_WARNING
0x14013d7e4  mov     cs:qword_1403B81E8, rax
0x14013d7eb  lea     rax, MSVML_WORKER_THREADS_ERROR
0x14013d7f2  mov     cs:qword_1403B81E0, rax
0x14013d7f9  lea     rax, MSVML_WORKER_THREADS_CRITICAL
0x14013d800  mov     cs:qword_1403B81D8, rax
0x14013d807  lea     rax, MSVML_WORKER_REFCOUNTED_INFO
0x14013d80e  mov     cs:qword_1403B8210, rax
0x14013d815  lea     rax, MSVML_WORKER_REFCOUNTED_WARNING
0x14013d81c  mov     cs:qword_1403B8208, rax
0x14013d823  lea     rax, MSVML_WORKER_REFCOUNTED_ERROR
0x14013d82a  mov     cs:qword_1403B8200, rax
0x14013d831  lea     rax, MSVML_WORKER_REFCOUNTED_CRITICAL
0x14013d838  mov     cs:qword_1403B81F8, rax
0x14013d83f  lea     rax, MSVML_WORKER_WMI_INFO
0x14013d846  mov     cs:qword_1403B8230, rax
0x14013d84d  lea     rax, MSVML_WORKER_WMI_WARNING
0x14013d854  mov     cs:qword_1403B8228, rax
0x14013d85b  lea     rax, MSVML_WORKER_WMI_ERROR
0x14013d862  mov     cs:qword_1403B8220, rax
0x14013d869  lea     rax, MSVML_WORKER_WMI_CRITICAL
0x14013d870  mov     cs:qword_1403B8218, rax
0x14013d877  lea     rax, MSVM_WORKER_MIGRATION_DEBUG_CRITICAL
0x14013d87e  mov     cs:qword_1403BBD38, rax
0x14013d885  mov     cs:qword_1403BBD78, rax
0x14013d88c  lea     rax, MSVDEV_BIOS_INFO
0x14013d893  mov     cs:qword_1403B9950, rax
0x14013d89a  lea     rax, MSVDEV_BIOS_WARNING
0x14013d8a1  mov     cs:qword_1403B9948, rax
0x14013d8a8  lea     rax, MSVDEV_BIOS_ERROR
0x14013d8af  mov     cs:qword_1403B9940, rax
0x14013d8b6  lea     rax, MSVDEV_BIOS_CRITICAL
0x14013d8bd  mov     cs:qword_1403B9938, rax
0x14013d8c4  lea     rax, MSVDEV_CMOS_INFO
0x14013d8cb  mov     cs:qword_1403B9970, rax
0x14013d8d2  lea     rax, MSVDEV_CMOS_WARNING
0x14013d8d9  mov     cs:qword_1403B9968, rax
0x14013d8e0  lea     rax, MSVDEV_CMOS_ERROR
0x14013d8e7  mov     cs:qword_1403BBD90, r8
0x14013d8ee  mov     cs:qword_1403BBD88, rdx
0x14013d8f5  mov     cs:qword_1403BBD80, rcx
0x14013d8fc  mov     cs:qword_1403B9960, rax
0x14013d903  lea     rax, MSVDEV_CMOS_CRITICAL
0x14013d90a  mov     cs:qword_1403B9958, rax
0x14013d911  lea     rax, MSVDEV_POWER_MANAGEMENT_INFO
0x14013d918  mov     cs:qword_1403B9990, rax
0x14013d91f  lea     rax, MSVDEV_POWER_MANAGEMENT_WARNING
0x14013d926  mov     cs:qword_1403B9988, rax
0x14013d92d  lea     rax, MSVDEV_POWER_MANAGEMENT_ERROR
0x14013d934  mov     cs:qword_1403B9980, rax
0x14013d93b  lea     rax, MSVDEV_POWER_MANAGEMENT_CRITICAL
0x14013d942  mov     cs:qword_1403B9978, rax
0x14013d949  lea     rax, MSVDEV_SM_BUS_INFO
0x14013d950  mov     cs:qword_1403B99B0, rax
0x14013d957  lea     rax, MSVDEV_SM_BUS_WARNING
0x14013d95e  mov     cs:qword_1403B99A8, rax
0x14013d965  lea     rax, MSVDEV_SM_BUS_ERROR
0x14013d96c  mov     cs:qword_1403B99A0, rax
0x14013d973  lea     rax, MSVDEV_SM_BUS_CRITICAL
0x14013d97a  mov     cs:qword_1403B9998, rax
0x14013d981  lea     rax, MSVDEV_ISA_BUS_INFO
0x14013d988  mov     cs:qword_1403B99D0, rax
0x14013d98f  lea     rax, MSVDEV_ISA_BUS_WARNING
0x14013d996  mov     cs:qword_1403B99C8, rax
0x14013d99d  lea     rax, MSVDEV_ISA_BUS_ERROR
0x14013d9a4  mov     cs:qword_1403B99C0, rax
0x14013d9ab  lea     rax, MSVDEV_ISA_BUS_CRITICAL
0x14013d9b2  mov     cs:qword_1403B99B8, rax
0x14013d9b9  lea     rax, MSVDEV_PCI_BUS_INFO
0x14013d9c0  mov     cs:qword_1403B99F0, rax
0x14013d9c7  lea     rax, MSVDEV_PCI_BUS_WARNING
0x14013d9ce  mov     cs:qword_1403B99E8, rax
0x14013d9d5  lea     rax, MSVDEV_PCI_BUS_ERROR
0x14013d9dc  mov     cs:qword_1403B99E0, rax
0x14013d9e3  lea     rax, MSVDEV_PCI_BUS_CRITICAL; "2("
0x14013d9ea  mov     cs:qword_1403B99D8, rax
0x14013d9f1  lea     rax, MSVDEV_APIC_INFO
0x14013d9f8  mov     cs:qword_1403B9A10, rax
0x14013d9ff  lea     rax, MSVDEV_APIC_WARNING
0x14013da06  mov     cs:qword_1403B9A08, rax
0x14013da0d  lea     rax, MSVDEV_APIC_ERROR
0x14013da14  mov     cs:qword_1403B9A00, rax
0x14013da1b  lea     rax, MSVDEV_APIC_CRITICAL
0x14013da22  mov     cs:qword_1403B99F8, rax
0x14013da29  lea     rax, MSVDEV_DMA_INFO
0x14013da30  mov     cs:qword_1403B9A30, rax
0x14013da37  lea     rax, MSVDEV_DMA_WARNING
0x14013da3e  mov     cs:qword_1403B9A28, rax
0x14013da45  lea     rax, MSVDEV_DMA_ERROR
0x14013da4c  mov     cs:qword_1403B9A20, rax
0x14013da53  lea     rax, MSVDEV_DMA_CRITICAL
0x14013da5a  mov     cs:qword_1403B9A18, rax
0x14013da61  lea     rax, MSVDEV_PIC_INFO
0x14013da68  mov     cs:qword_1403B9A50, rax
0x14013da6f  lea     rax, MSVDEV_PIC_WARNING
0x14013da76  mov     cs:qword_1403B9A48, rax
0x14013da7d  lea     rax, MSVDEV_PIC_ERROR
0x14013da84  mov     cs:qword_1403B9A40, rax
0x14013da8b  lea     rax, MSVDEV_PIC_CRITICAL
0x14013da92  mov     cs:qword_1403B9A38, rax
0x14013da99  lea     rax, MSVDEV_PIT_INFO
0x14013daa0  mov     cs:qword_1403B9A70, rax
0x14013daa7  lea     rax, MSVDEV_PIT_WARNING
0x14013daae  mov     cs:qword_1403B9A68, rax
0x14013dab5  lea     rax, MSVDEV_PIT_ERROR
0x14013dabc  mov     cs:qword_1403B9A60, rax
0x14013dac3  lea     rax, MSVDEV_PIT_CRITICAL
0x14013daca  mov     cs:qword_1403B9A58, rax
0x14013dad1  lea     rax, MSVDEV_SUPER_IO_INFO
0x14013dad8  mov     cs:qword_1403B9A90, rax
0x14013dadf  lea     rax, MSVDEV_SUPER_IO_WARNING
0x14013dae6  mov     cs:qword_1403B9A88, rax
0x14013daed  lea     rax, MSVDEV_SUPER_IO_ERROR
0x14013daf4  mov     cs:qword_1403B9A80, rax
0x14013dafb  lea     rax, MSVDEV_SUPER_IO_CRITICAL
0x14013db02  mov     cs:qword_1403B9A78, rax
0x14013db09  lea     rax, MSVDEV_SERIAL_CONTROLLER_INFO
0x14013db10  mov     cs:qword_1403B9AB0, rax
0x14013db17  lea     rax, MSVDEV_SERIAL_CONTROLLER_WARNING
0x14013db1e  mov     cs:qword_1403B9AA8, rax
0x14013db25  lea     rax, MSVDEV_SERIAL_CONTROLLER_ERROR
0x14013db2c  mov     cs:qword_1403B9AA0, rax
0x14013db33  lea     rax, MSVDEV_SERIAL_CONTROLLER_CRITICAL
0x14013db3a  mov     cs:qword_1403B9A98, rax
0x14013db41  lea     r8, MSVDEV_MOUSE_INFO; "|)"
0x14013db48  lea     rax, MSVDEV_KEYBOARD_INFO
0x14013db4f  mov     cs:qword_1403B9AF0, r8
0x14013db56  mov     cs:qword_1403B9AD0, rax
0x14013db5d  lea     rdx, MSVDEV_MOUSE_WARNING
0x14013db64  lea     rax, MSVDEV_KEYBOARD_WARNING
0x14013db6b  mov     cs:qword_1403B9AE8, rdx
0x14013db72  mov     cs:qword_1403B9AC8, rax
0x14013db79  lea     rcx, MSVDEV_MOUSE_ERROR
0x14013db80  lea     rax, MSVDEV_KEYBOARD_ERROR
0x14013db87  mov     cs:qword_1403B9AE0, rcx
0x14013db8e  mov     cs:qword_1403B9AC0, rax
0x14013db95  lea     rax, MSVDEV_KEYBOARD_CRITICAL
0x14013db9c  mov     cs:qword_1403B9AB8, rax
0x14013dba3  lea     rax, MSVDEV_MOUSE_CRITICAL
0x14013dbaa  mov     cs:qword_1403B9AD8, rax
0x14013dbb1  mov     cs:qword_1403B9CD8, rax
0x14013dbb8  lea     rax, MSVDEV_FLOPPY_CONTROLLER_INFO
0x14013dbbf  mov     cs:qword_1403B9B10, rax
0x14013dbc6  lea     rax, MSVDEV_FLOPPY_CONTROLLER_WARNING
0x14013dbcd  mov     cs:qword_1403B9B08, rax
0x14013dbd4  lea     rax, MSVDEV_FLOPPY_CONTROLLER_ERROR
0x14013dbdb  mov     cs:qword_1403B9B00, rax
0x14013dbe2  lea     rax, MSVDEV_FLOPPY_CONTROLLER_CRITICAL
0x14013dbe9  mov     cs:qword_1403B9AF8, rax
0x14013dbf0  lea     rax, MSVDEV_FLOPPY_DRIVE_INFO
0x14013dbf7  mov     cs:qword_1403B9B30, rax
0x14013dbfe  lea     rax, MSVDEV_FLOPPY_DRIVE_WARNING
0x14013dc05  mov     cs:qword_1403B9B28, rax
0x14013dc0c  lea     rax, MSVDEV_FLOPPY_DRIVE_ERROR
0x14013dc13  mov     cs:qword_1403B9B20, rax
0x14013dc1a  lea     rax, MSVDEV_FLOPPY_DRIVE_CRITICAL
0x14013dc21  mov     cs:qword_1403B9B18, rax
0x14013dc28  lea     rax, MSVDEV_IDE_CONTROLLER_INFO
0x14013dc2f  mov     cs:qword_1403B9B50, rax
0x14013dc36  lea     rax, MSVDEV_IDE_CONTROLLER_WARNING
0x14013dc3d  mov     cs:qword_1403B9B48, rax
0x14013dc44  lea     rax, MSVDEV_IDE_CONTROLLER_ERROR
0x14013dc4b  mov     cs:qword_1403B9B40, rax
0x14013dc52  lea     rax, MSVDEV_IDE_CONTROLLER_CRITICAL
0x14013dc59  mov     cs:qword_1403B9B38, rax
0x14013dc60  lea     rax, MSVDEV_IDE_ATTACHMENT_INFO
0x14013dc67  mov     cs:qword_1403B9B70, rax
0x14013dc6e  lea     rax, MSVDEV_IDE_ATTACHMENT_WARNING
0x14013dc75  mov     cs:qword_1403B9B68, rax
0x14013dc7c  lea     rax, MSVDEV_IDE_ATTACHMENT_ERROR
0x14013dc83  mov     cs:qword_1403B9B60, rax
0x14013dc8a  lea     rax, MSVDEV_IDE_ATTACHMENT_CRITICAL
0x14013dc91  mov     cs:qword_1403B9B58, rax
0x14013dc98  lea     rax, MSVDEV_SCSI_CONTROLLER_INFO
0x14013dc9f  mov     cs:qword_1403B9B90, rax
0x14013dca6  lea     rax, MSVDEV_SCSI_CONTROLLER_WARNING
0x14013dcad  mov     cs:qword_1403B9B88, rax
0x14013dcb4  lea     rax, MSVDEV_SCSI_CONTROLLER_ERROR
0x14013dcbb  mov     cs:qword_1403B9B80, rax
0x14013dcc2  lea     rax, MSVDEV_SCSI_CONTROLLER_CRITICAL
0x14013dcc9  mov     cs:qword_1403B9B78, rax
0x14013dcd0  lea     rax, MSVDEV_SCSI_BUS_INFO
0x14013dcd7  mov     cs:qword_1403B9BB0, rax
0x14013dcde  lea     rax, MSVDEV_SCSI_BUS_WARNING
0x14013dce5  mov     cs:qword_1403B9BA8, rax
0x14013dcec  lea     rax, MSVDEV_SCSI_BUS_ERROR
0x14013dcf3  mov     cs:qword_1403B9BA0, rax
0x14013dcfa  lea     rax, MSVDEV_SCSI_BUS_CRITICAL
0x14013dd01  mov     cs:qword_1403B9B98, rax
0x14013dd08  lea     rax, MSVDEV_SCSI_ATTACHMENT_INFO
0x14013dd0f  mov     cs:qword_1403B9BD0, rax
0x14013dd16  lea     rax, MSVDEV_SCSI_ATTACHMENT_WARNING
0x14013dd1d  mov     cs:qword_1403B9BC8, rax
0x14013dd24  lea     rax, MSVDEV_SCSI_ATTACHMENT_ERROR
0x14013dd2b  mov     cs:qword_1403B9BC0, rax
0x14013dd32  lea     rax, MSVDEV_SCSI_ATTACHMENT_CRITICAL
0x14013dd39  mov     cs:qword_1403B9BB8, rax
0x14013dd40  lea     rax, MSVDEV_MEDIA_INFO
0x14013dd47  mov     cs:qword_1403B9BF0, rax
0x14013dd4e  lea     rax, MSVDEV_MEDIA_WARNING
0x14013dd55  mov     cs:qword_1403B9CF0, r8
0x14013dd5c  mov     cs:qword_1403B9CE8, rdx
0x14013dd63  mov     cs:qword_1403B9CE0, rcx
0x14013dd6a  mov     cs:qword_1403B9BE8, rax
0x14013dd71  lea     r8, MSVDEV_VIDEO_CONTROLLER_INFO
0x14013dd78  lea     rax, MSVDEV_MEDIA_ERROR
0x14013dd7f  mov     cs:qword_1403B9C50, r8
0x14013dd86  mov     cs:qword_1403B9BE0, rax
0x14013dd8d  lea     rdx, MSVDEV_VIDEO_CONTROLLER_WARNING; ">+"
0x14013dd94  lea     rax, MSVDEV_MEDIA_CRITICAL
0x14013dd9b  mov     cs:qword_1403B9C48, rdx
0x14013dda2  mov     cs:qword_1403B9BD8, rax
0x14013dda9  lea     rcx, MSVDEV_VIDEO_CONTROLLER_ERROR
0x14013ddb0  lea     rax, MSVDEV_HARD_DRIVE_INFO
0x14013ddb7  mov     cs:qword_1403B9C40, rcx
0x14013ddbe  mov     cs:qword_1403B9C10, rax
0x14013ddc5  lea     rax, MSVDEV_HARD_DRIVE_WARNING
0x14013ddcc  mov     cs:qword_1403B9C08, rax
0x14013ddd3  lea     rax, MSVDEV_HARD_DRIVE_ERROR
0x14013ddda  mov     cs:qword_1403B9C00, rax
0x14013dde1  lea     rax, MSVDEV_HARD_DRIVE_CRITICAL
0x14013dde8  mov     cs:qword_1403B9BF8, rax
0x14013ddef  lea     rax, MSVDEV_ETHERNET_INFO
0x14013ddf6  mov     cs:qword_1403B9C30, rax
0x14013ddfd  lea     rax, MSVDEV_ETHERNET_WARNING
0x14013de04  mov     cs:qword_1403B9C28, rax
0x14013de0b  lea     rax, MSVDEV_ETHERNET_ERROR
0x14013de12  mov     cs:qword_1403B9C20, rax
0x14013de19  lea     rax, MSVDEV_ETHERNET_CRITICAL
0x14013de20  mov     cs:qword_1403B9C18, rax
0x14013de27  lea     rax, MSVDEV_VIDEO_CONTROLLER_CRITICAL; "R+"
0x14013de2e  mov     cs:qword_1403B9C38, rax
0x14013de35  mov     cs:qword_1403B9CB8, rax
0x14013de3c  lea     rax, MSVDEV_REPOSITORY_INFO
0x14013de43  mov     cs:qword_1403B9C70, rax
0x14013de4a  lea     rax, MSVDEV_REPOSITORY_WARNING; "f+"
0x14013de51  mov     cs:qword_1403B9C68, rax
0x14013de58  lea     rax, MSVDEV_REPOSITORY_ERROR
0x14013de5f  mov     cs:qword_1403B9C60, rax
0x14013de66  lea     rax, MSVDEV_REPOSITORY_CRITICAL
0x14013de6d  mov     cs:qword_1403B9C58, rax
0x14013de74  lea     rax, MSVDEV_REMOTING_INFO
0x14013de7b  mov     cs:qword_1403B9C90, rax
0x14013de82  lea     rax, MSVDEV_REMOTING_WARNING
0x14013de89  mov     cs:qword_1403B9C88, rax
0x14013de90  lea     rax, MSVDEV_REMOTING_ERROR
0x14013de97  mov     cs:qword_1403B9C80, rax
0x14013de9e  lea     rax, MSVDEV_REMOTING_CRITICAL
0x14013dea5  mov     cs:qword_1403B9C78, rax
0x14013deac  lea     rax, MSVDEV_HID_INFO
0x14013deb3  mov     cs:qword_1403B9CB0, rax
0x14013deba  lea     rax, MSVDEV_HID_WARNING
0x14013dec1  mov     cs:qword_1403B9CA8, rax
0x14013dec8  lea     rax, MSVDEV_HID_ERROR
0x14013decf  mov     cs:qword_1403B9CA0, rax
0x14013ded6  lea     rax, MSVDEV_HID_CRITICAL
  ... truncated ...
```
