# CLogonController::PromptForCredentials(ulong,_CREDUI_CONTEXT,CREDUI_INFO_INTERNAL_CONTEXT,ulong,ulong,uchar *,ulong,int,ulong,uchar * *,ulong *,int *,ulong *,ulong *)

- ea: `0x180078680`
- end: `0x180078912`
- name: `?PromptForCredentials@CLogonController@@UEAAJKU_CREDUI_CONTEXT@@UCREDUI_INFO_INTERNAL_CONTEXT@@KKPEAEKHKPEAPEAEPEAKPEAH44@Z`
- size: `658`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation`

## callees

- `0x18001db70`
- `0x18001f3a0`
- `0x1800208b4`
- `0x18002318c`
- `0x18002d920`
- `0x18002f554`
- `0x18002f760`
- `0x18005b3e4`
- `0x18005d488`
- `0x18006c000`
- `0x18006cad0`
- `0x18007486c`
- `0x180078680`
- `0x180079f94`
- `0x18007becc`
- `0x18009b790`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x180078790`
- `KERNEL32!GetCurrentProcessId` at `0x180078790`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetDesktopWindow` at `0x180078866`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetDesktopWindow` at `0x180078866`
- `credui!CredUIPromptForWindowsCredentialsWorker` at `0x1800788ca`
- `credui!CredUIPromptForWindowsCredentialsWorker` at `0x1800788ca`

## pseudocode

```c

```
