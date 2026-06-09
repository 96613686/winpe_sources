# MailMergeDlg::HrLoadDocFile(int,int)

- ea: `0x141ac2b54`
- end: `0x141ac37b0`
- name: `?HrLoadDocFile@MailMergeDlg@@AEAAJHH@Z`
- size: `3164`
- prototype: `__int64 __fastcall(MailMergeDlg *__hidden this, int, int)`
- caller_count: `3`
- callee_count: `27`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x141ac3f20`
- `0x141ac3ff0`
- `0x141ac4620`

## callees

- `0x140049040`
- `0x1400d7910`
- `0x1400dd0bc`
- `0x1400dd680`
- `0x1400dd710`
- `0x14015423c`
- `0x14024ab3c`
- `0x1402c39b8`
- `0x1402c3b58`
- `0x1402ca078`
- `0x1402fcca8`
- `0x140503f00`
- `0x140509800`
- `0x14071a1d0`
- `0x1407e99f0`
- `0x1409c72fc`
- `0x140dfe5e4`
- `0x141170e78`
- `0x1416f20c8`
- `0x141993f1c`
- `0x141ac1db4`
- `0x141ac2638`
- `0x141ac27a4`
- `0x141ac2a08`
- `0x141ac2b54`
- `0x141ac3cf0`
- `0x141ac3eb0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x141ac32d5`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x141ac32d5`
- `KERNEL32!GetTempPathW` at `0x141ac327b`
- `KERNEL32!GetTempPathW` at `0x141ac327b`
- `KERNEL32!CloseHandle` at `0x141ac2dea`
- `KERNEL32!CloseHandle` at `0x141ac2dea`
- `KERNEL32!GetLastError` at `0x141ac2d43`
- `KERNEL32!GetLastError` at `0x141ac3285`
- `KERNEL32!GetLastError` at `0x141ac2d43`
- `KERNEL32!GetLastError` at `0x141ac3285`
- `OLMAPI32!EtwTraceErrorTag` at `0x141ac2bfa`
- `OLMAPI32!EtwTraceErrorTag` at `0x141ac2d66`
- `OLMAPI32!EtwTraceErrorTag` at `0x141ac2bfa`
- `OLMAPI32!EtwTraceErrorTag` at `0x141ac2d66`
- `ole32!CoTaskMemFree` at `0x141ac2c6c`
- `ole32!CoTaskMemFree` at `0x141ac305d`
- `ole32!CoTaskMemFree` at `0x141ac32ea`
- `ole32!CoTaskMemFree` at `0x141ac3386`
- `ole32!CoTaskMemFree` at `0x141ac2c6c`
- `ole32!CoTaskMemFree` at `0x141ac305d`
- `ole32!CoTaskMemFree` at `0x141ac32ea`
- `ole32!CoTaskMemFree` at `0x141ac3386`
- `USER32!SendMessageW` at `0x141ac2ce6`
- `USER32!SendMessageW` at `0x141ac30b9`
- `USER32!SendMessageW` at `0x141ac3353`
- `USER32!SendMessageW` at `0x141ac33e2`
- `USER32!SendMessageW` at `0x141ac36d2`
- `USER32!SendMessageW` at `0x141ac2ce6`
- `USER32!SendMessageW` at `0x141ac30b9`
- `USER32!SendMessageW` at `0x141ac3353`
- `USER32!SendMessageW` at `0x141ac33e2`
- `USER32!SendMessageW` at `0x141ac36d2`
- `USER32!SendDlgItemMessageA` at `0x141ac2d03`
- `USER32!SendDlgItemMessageA` at `0x141ac3081`
- `USER32!SendDlgItemMessageA` at `0x141ac331b`
- `USER32!SendDlgItemMessageA` at `0x141ac3370`
- `USER32!SendDlgItemMessageA` at `0x141ac33aa`
- `USER32!SendDlgItemMessageA` at `0x141ac35b6`
- `USER32!SendDlgItemMessageA` at `0x141ac362e`
- `USER32!SendDlgItemMessageA` at `0x141ac2d03`
- `USER32!SendDlgItemMessageA` at `0x141ac3081`
- `USER32!SendDlgItemMessageA` at `0x141ac331b`
- `USER32!SendDlgItemMessageA` at `0x141ac3370`
- `USER32!SendDlgItemMessageA` at `0x141ac33aa`
- `USER32!SendDlgItemMessageA` at `0x141ac35b6`
- `USER32!SendDlgItemMessageA` at `0x141ac362e`
- `USER32!GetDlgItem` at `0x141ac2cae`
- `USER32!GetDlgItem` at `0x141ac301f`
- `USER32!GetDlgItem` at `0x141ac369e`
- `USER32!GetDlgItem` at `0x141ac3711`
- `USER32!GetDlgItem` at `0x141ac2cae`
- `USER32!GetDlgItem` at `0x141ac301f`
- `USER32!GetDlgItem` at `0x141ac369e`
- `USER32!GetDlgItem` at `0x141ac3711`
- `USER32!SendMessageA` at `0x141ac3726`
- `USER32!SendMessageA` at `0x141ac3726`
- `Mso98Win32Client!__imp_?MsoCreateFileW@Monitoring@FileIO@@YAPEAXPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z` at `0x141ac2d30`
- `Mso98Win32Client!__imp_?MsoCreateFileW@Monitoring@FileIO@@YAPEAXPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z` at `0x141ac2d30`
- `Mso20Win32Client!__imp_?MsoFRegKeyExists@@YAHPEBU_msoreg@@@Z` at `0x141ac360a`
- `Mso20Win32Client!__imp_?MsoFRegKeyExists@@YAHPEBU_msoreg@@@Z` at `0x141ac360a`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x141ac2d9c`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x141ac2dac`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x141ac33f1`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x141ac3405`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x141ac36e5`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x141ac2d9c`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x141ac2dac`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x141ac33f1`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x141ac3405`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x141ac36e5`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x141ac2c5f`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x141ac32b5`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x141ac2c5f`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x141ac32b5`

## pseudocode

```c

```
