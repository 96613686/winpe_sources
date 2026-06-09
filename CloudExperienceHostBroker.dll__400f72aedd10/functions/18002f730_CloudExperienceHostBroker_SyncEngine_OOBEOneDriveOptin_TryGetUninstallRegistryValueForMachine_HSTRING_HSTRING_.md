# CloudExperienceHostBroker::SyncEngine::OOBEOneDriveOptin::TryGetUninstallRegistryValueForMachine(HSTRING__ *,HSTRING__ *,HSTRING__ * *,uchar *)

- ea: `0x18002f730`
- end: `0x18002f791`
- name: `?TryGetUninstallRegistryValueForMachine@OOBEOneDriveOptin@SyncEngine@CloudExperienceHostBroker@@UEAAJPEAUHSTRING__@@0PEAPEAU4@PEAE@Z`
- size: `97`
- prototype: `int(CloudExperienceHostBroker::SyncEngine::OOBEOneDriveOptin *__hidden this, HSTRING, HSTRING, HSTRING *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18002f4f8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002f74a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002f758`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002f74a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002f758`

## string_xrefs

- `0x18002f763`: `Software\Microsoft\Windows\CurrentVersion\Uninstall`

## pseudocode

```c
__int64 __fastcall CloudExperienceHostBroker::SyncEngine::OOBEOneDriveOptin::TryGetUninstallRegistryValueForMachine(
        CloudExperienceHostBroker::SyncEngine::OOBEOneDriveOptin *this,
        HSTRING a2,
        HSTRING a3,
        HSTRING *a4,
        CloudExperienceHostBroker::SyncEngine::OOBEOneDriveOptin *a5)
{
  const WCHAR *lpValueName; // rdi
  const unsigned __int16 *StringRawBuffer; // rax
  HKEY v9; // rdx

  lpValueName = WindowsGetStringRawBuffer(a3, 0);
  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  return CloudExperienceHostBroker::SyncEngine::OOBEOneDriveOptin::TryGetRegistryValueHelper(
           a5,
           v9,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\Uninstall",
           StringRawBuffer,
           lpValueName,
           (HKEY)a4,
           (bool *)a5);
}

```

## disassembly

```asm
0x18002f730  mov     [rsp+arg_0], rbx
0x18002f735  mov     [rsp+arg_8], rsi
0x18002f73a  push    rdi
0x18002f73b  sub     rsp, 40h
0x18002f73f  mov     rbx, rdx
0x18002f742  mov     rcx, r8; string
0x18002f745  xor     edx, edx; length
0x18002f747  mov     rsi, r9
0x18002f74a  call    cs:__imp_WindowsGetStringRawBuffer
0x18002f750  xor     edx, edx; length
0x18002f752  mov     rcx, rbx; string
0x18002f755  mov     rdi, rax
0x18002f758  call    cs:__imp_WindowsGetStringRawBuffer
0x18002f75e  mov     rcx, qword ptr [rsp+48h+arg_20]; this
0x18002f763  lea     r8, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002f76a  mov     qword ptr [rsp+48h+var_18], rcx; DWORD
0x18002f76f  mov     r9, rax; unsigned __int16 *
0x18002f772  mov     [rsp+48h+hKey], rsi; hKey
0x18002f777  mov     [rsp+48h+lpValueName], rdi; lpValueName
0x18002f77c  call    ?TryGetRegistryValueHelper@OOBEOneDriveOptin@SyncEngine@CloudExperienceHostBroker@@AEAAJPEAUHKEY__@@PEBG11PEAPEAUHSTRING__@@PEAE@Z; CloudExperienceHostBroker::SyncEngine::OOBEOneDriveOptin::TryGetRegistryValueHelper(HKEY__ *,ushort const *,ushort const *,ushort const *,HSTRING__ * *,uchar *)
0x18002f781  mov     rbx, [rsp+48h+arg_0]
0x18002f786  mov     rsi, [rsp+48h+arg_8]
0x18002f78b  add     rsp, 40h
0x18002f78f  pop     rdi
0x18002f790  retn
```
