# ScanForUpdatesWorker::~ScanForUpdatesWorker(void)

- ea: `0x18000d7dc`
- end: `0x18000d80d`
- name: `??1ScanForUpdatesWorker@@QEAA@XZ`
- size: `49`
- prototype: `void __fastcall(wil::details **this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x18000da60`

## callees

- `0x180005c74`
- `0x18000d5c0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d7fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d7fa`

## pseudocode

```c
void __fastcall ScanForUpdatesWorker::~ScanForUpdatesWorker(wil::details **this, void *a2)
{
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    this + 2,
    a2);
  std::unique_ptr<DownloadAndInstallPendingUpdatesWorker>::~unique_ptr<DownloadAndInstallPendingUpdatesWorker>(this + 1);
  WindowsDeleteString((HSTRING)*this);
  *this = 0;
}

```

## disassembly

```asm
0x18000d7dc  push    rbx
0x18000d7de  sub     rsp, 20h
0x18000d7e2  mov     rbx, rcx
0x18000d7e5  add     rcx, 10h
0x18000d7e9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000d7ee  lea     rcx, [rbx+8]
0x18000d7f2  call    ??1?$unique_ptr@VDownloadAndInstallPendingUpdatesWorker@@U?$default_delete@VDownloadAndInstallPendingUpdatesWorker@@@std@@@std@@QEAA@XZ; std::unique_ptr<DownloadAndInstallPendingUpdatesWorker>::~unique_ptr<DownloadAndInstallPendingUpdatesWorker>(void)
0x18000d7f7  mov     rcx, [rbx]; string
0x18000d7fa  call    cs:__imp_WindowsDeleteString
0x18000d800  mov     qword ptr [rbx], 0
0x18000d807  add     rsp, 20h
0x18000d80b  pop     rbx
0x18000d80c  retn
```
