# vemgr::ProcessNotifyCallbackEx(_KPROCESS *,void *,_PS_CREATE_NOTIFY_INFO *)

- ea: `0x180018ea0`
- end: `0x18001900e`
- name: `?ProcessNotifyCallbackEx@vemgr@@YAXPEAU_KPROCESS@@PEAXPEAU_PS_CREATE_NOTIFY_INFO@@@Z`
- size: `366`
- prototype: `void __stdcall(PEPROCESS Process, HANDLE ProcessId, PPS_CREATE_NOTIFY_INFO CreateInfo)`
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000a9e4`
- `0x18000fd5c`
- `0x180016f64`
- `0x180018ea0`
- `0x18001a594`
- `0x18001b3cc`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x180018fdc`
- `ntoskrnl!ExFreePoolWithTag` at `0x180018fdc`
- `ntoskrnl!RtlInitUnicodeString` at `0x180018eda`
- `ntoskrnl!RtlInitUnicodeString` at `0x180018eda`
- `FLTMGR!FltReleaseFileNameInformation` at `0x180018f3b`
- `FLTMGR!FltReleaseFileNameInformation` at `0x180018f3b`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x180018f0a`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x180018f0a`

## string_xrefs

- `0x180018fbd`: `CreateProcessCallback::process_create_notification() - Failed to create the virtual process. Error: %d`

## pseudocode

```c
void __fastcall vemgr::ProcessNotifyCallbackEx(PEPROCESS Process, HANDLE ProcessId, PPS_CREATE_NOTIFY_INFO CreateInfo)
{
  unsigned int v4; // esi
  struct _FILE_OBJECT *FileObject; // rcx
  NTSTATUS FileNameInformationUnsafe; // ebx
  __int64 v7; // rcx
  __int64 v8; // r8
  PCUNICODE_STRING CommandLine; // r14
  int ParentProcessId; // edi
  __int64 *v11; // rbx
  __int64 v12; // rcx
  unsigned int v13; // ebx
  __int64 v14; // r8
  __int64 v15; // [rsp+30h] [rbp-20h] BYREF
  PVOID P; // [rsp+38h] [rbp-18h]
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-10h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+80h] [rbp+30h] BYREF

  v4 = (unsigned int)ProcessId;
  if ( !CreateInfo )
  {
    vemgr::CreateProcessCallback<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::process_destroy_notification(
      *((__int64 **)vemgr::g_pDeviceExtn + 6),
      (unsigned int)ProcessId,
      0);
    return;
  }
  v15 = 0;
  P = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  FileObject = CreateInfo->FileObject;
  if ( FileObject )
  {
    FileNameInformation = 0;
    FileNameInformationUnsafe = FltGetFileNameInformationUnsafe(FileObject, 0, 0x101u, &FileNameInformation);
    if ( FileNameInformationUnsafe >= 0 )
    {
      FileNameInformationUnsafe = appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(
                                    &v15,
                                    FileNameInformation->Name.Buffer,
                                    (unsigned __int64)FileNameInformation->Name.Length >> 1);
      FltReleaseFileNameInformation(FileNameInformation);
      if ( FileNameInformationUnsafe >= 0 )
      {
        CommandLine = CreateInfo->CommandLine;
        ParentProcessId = (int)CreateInfo->ParentProcessId;
        v11 = (__int64 *)*((_QWORD *)vemgr::g_pDeviceExtn + 6);
        if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
          McTemplateK0q_EtwWriteTransfer(v7, VEMGR_Process_Launch_Start, v8, v4);
        v13 = VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::AddProcess(
                *v11,
                v4,
                ParentProcessId,
                (int)CommandLine,
                (__int64)&v15);
        if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
          McTemplateK0q_EtwWriteTransfer(v12, VEMGR_Process_Launch_Finish, v14, v4);
        if ( v13 != -1073741772 && v13 )
          LogWrite(
            1,
            0,
            L"CreateProcessCallback::process_create_notification() - Failed to create the virtual process. Error: %d",
            v13);
        goto LABEL_14;
      }
    }
  }
  else
  {
    FileNameInformationUnsafe = -1073741811;
  }
  LogWrite(
    1,
    0,
    L"vemgr::ProcessNotifyCallbackEx() - Error getting normalized process imange file name. Error %d.",
    (unsigned int)FileNameInformationUnsafe);
LABEL_14:
  if ( P )
    ExFreePoolWithTag(P, 0);
}

```

## disassembly

```asm
0x180018ea0  mov     [rsp-18h+arg_0], rbx
0x180018ea5  mov     [rsp-18h+arg_8], rsi
0x180018eaa  push    rbp
0x180018eab  push    rdi
0x180018eac  push    r14
0x180018eae  mov     rbp, rsp
0x180018eb1  sub     rsp, 50h
0x180018eb5  mov     rdi, r8
0x180018eb8  mov     rsi, rdx
0x180018ebb  test    r8, r8
0x180018ebe  jz      loc_180018FEA
0x180018ec4  xor     edx, edx; SourceString
0x180018ec6  mov     [rbp+var_20], 0
0x180018ece  lea     rcx, [rbp+DestinationString]; DestinationString
0x180018ed2  mov     [rbp+P], 0
0x180018eda  call    cs:__imp_RtlInitUnicodeString
0x180018ee1  nop     dword ptr [rax+rax+00h]
0x180018ee6  mov     rcx, [rdi+28h]; FileObject
0x180018eea  test    rcx, rcx
0x180018eed  jnz     short loc_180018EF6
0x180018eef  mov     ebx, 0C000000Dh
0x180018ef4  jmp     short loc_180018F4B
0x180018ef6  lea     r9, [rbp+FileNameInformation]; FileNameInformation
0x180018efa  mov     [rbp+FileNameInformation], 0
0x180018f02  xor     edx, edx; Instance
0x180018f04  mov     r8d, 101h; NameOptions
0x180018f0a  call    cs:__imp_FltGetFileNameInformationUnsafe
0x180018f11  nop     dword ptr [rax+rax+00h]
0x180018f16  mov     ebx, eax
0x180018f18  test    eax, eax
0x180018f1a  js      short loc_180018F4B
0x180018f1c  mov     rdx, [rbp+FileNameInformation]
0x180018f20  lea     rcx, [rbp+var_20]
0x180018f24  movzx   r8d, word ptr [rdx+8]
0x180018f29  mov     rdx, [rdx+10h]
0x180018f2d  shr     r8, 1
0x180018f30  call    ?assign@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEAAJPEB_W_K@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(wchar_t const *,unsigned __int64)
0x180018f35  mov     rcx, [rbp+FileNameInformation]; FileNameInformation
0x180018f39  mov     ebx, eax
0x180018f3b  call    cs:__imp_FltReleaseFileNameInformation
0x180018f42  nop     dword ptr [rax+rax+00h]
0x180018f47  test    ebx, ebx
0x180018f49  jns     short loc_180018F54
0x180018f4b  lea     r8, aVemgrProcessno; "vemgr::ProcessNotifyCallbackEx() - Erro"...
0x180018f52  jmp     short loc_180018FC4
0x180018f54  test    cs:Microsoft_AppV_SharedPerformanceEnableBits, 1
0x180018f5b  mov     rax, cs:?g_pDeviceExtn@vemgr@@3PEAUDEVICE_EXTENSION@1@EA; vemgr::DEVICE_EXTENSION * vemgr::g_pDeviceExtn
0x180018f62  mov     r14, [rdi+38h]
0x180018f66  mov     edi, [rdi+10h]
0x180018f69  mov     rbx, [rax+30h]
0x180018f6d  jz      short loc_180018F7E
0x180018f6f  mov     r9d, esi
0x180018f72  lea     rdx, VEMGR_Process_Launch_Start
0x180018f79  call    McTemplateK0q_EtwWriteTransfer
0x180018f7e  mov     rcx, [rbx]
0x180018f81  lea     rax, [rbp+var_20]
0x180018f85  mov     r9, r14
0x180018f88  mov     [rsp+50h+var_30], rax
0x180018f8d  mov     r8d, edi
0x180018f90  mov     edx, esi
0x180018f92  call    ?AddProcess@?$VirtualEnvironmentManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJKKPEBU_UNICODE_STRING@@AEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@Z; VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::AddProcess(ulong,ulong,_UNICODE_STRING const *,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &)
0x180018f97  test    cs:Microsoft_AppV_SharedPerformanceEnableBits, 1
0x180018f9e  mov     ebx, eax
0x180018fa0  jz      short loc_180018FB1
0x180018fa2  mov     r9d, esi
0x180018fa5  lea     rdx, VEMGR_Process_Launch_Finish
0x180018fac  call    McTemplateK0q_EtwWriteTransfer
0x180018fb1  cmp     ebx, 0C0000034h
0x180018fb7  jz      short loc_180018FD1
0x180018fb9  test    ebx, ebx
0x180018fbb  jz      short loc_180018FD1
0x180018fbd  lea     r8, aCreateprocessc; "CreateProcessCallback::process_create_n"...
0x180018fc4  xor     edx, edx
0x180018fc6  mov     r9d, ebx
0x180018fc9  lea     ecx, [rdx+1]
0x180018fcc  call    LogWrite
0x180018fd1  mov     rcx, [rbp+P]; P
0x180018fd5  test    rcx, rcx
0x180018fd8  jz      short loc_180018FFA
0x180018fda  xor     edx, edx; Tag
0x180018fdc  call    cs:__imp_ExFreePoolWithTag
0x180018fe3  nop     dword ptr [rax+rax+00h]
0x180018fe8  jmp     short loc_180018FFA
0x180018fea  mov     rcx, cs:?g_pDeviceExtn@vemgr@@3PEAUDEVICE_EXTENSION@1@EA; vemgr::DEVICE_EXTENSION * vemgr::g_pDeviceExtn
0x180018ff1  mov     rcx, [rcx+30h]
0x180018ff5  call    ?process_destroy_notification@?$CreateProcessCallback@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@vemgr@@QEAAJPEAX@Z; vemgr::CreateProcessCallback<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::process_destroy_notification(void *)
0x180018ffa  mov     rbx, [rsp+50h+arg_0]
0x180018fff  mov     rsi, [rsp+50h+arg_8]
0x180019004  add     rsp, 50h
0x180019008  pop     r14
0x18001900a  pop     rdi
0x18001900b  pop     rbp
0x18001900c  retn
```
