# MailMergeDlg::HrLoadDocFile(int,int)

- ea: `0x141ac2c14`
- end: `0x141ac3870`
- name: `?HrLoadDocFile@MailMergeDlg@@AEAAJHH@Z`
- size: `3164`
- prototype: `__int64 __fastcall(MailMergeDlg *__hidden this, int, int)`
- caller_count: `3`
- callee_count: `27`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x141ac3fe0`
- `0x141ac40b0`
- `0x141ac46e0`

## callees

- `0x140049040`
- `0x1400d7900`
- `0x1400dd0ac`
- `0x1400dd670`
- `0x1400dd700`
- `0x14015427c`
- `0x14024b31c`
- `0x1402c4258`
- `0x1402c43f8`
- `0x1402ca8f8`
- `0x1402fd528`
- `0x1405049f0`
- `0x14050a2e0`
- `0x140701290`
- `0x1407e9990`
- `0x1409c744c`
- `0x140dfe694`
- `0x141170f38`
- `0x1416f2188`
- `0x141993fdc`
- `0x141ac1e74`
- `0x141ac26f8`
- `0x141ac2864`
- `0x141ac2ac8`
- `0x141ac2c14`
- `0x141ac3db0`
- `0x141ac3f70`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x141ac3395`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x141ac3395`
- `KERNEL32!GetTempPathW` at `0x141ac333b`
- `KERNEL32!GetTempPathW` at `0x141ac333b`
- `KERNEL32!CloseHandle` at `0x141ac2eaa`
- `KERNEL32!CloseHandle` at `0x141ac2eaa`
- `KERNEL32!GetLastError` at `0x141ac2e03`
- `KERNEL32!GetLastError` at `0x141ac3345`
- `KERNEL32!GetLastError` at `0x141ac2e03`
- `KERNEL32!GetLastError` at `0x141ac3345`
- `OLMAPI32!EtwTraceErrorTag` at `0x141ac2cba`
- `OLMAPI32!EtwTraceErrorTag` at `0x141ac2e26`
- `OLMAPI32!EtwTraceErrorTag` at `0x141ac2cba`
- `OLMAPI32!EtwTraceErrorTag` at `0x141ac2e26`
- `ole32!CoTaskMemFree` at `0x141ac2d2c`
- `ole32!CoTaskMemFree` at `0x141ac311d`
- `ole32!CoTaskMemFree` at `0x141ac33aa`
- `ole32!CoTaskMemFree` at `0x141ac3446`
- `ole32!CoTaskMemFree` at `0x141ac2d2c`
- `ole32!CoTaskMemFree` at `0x141ac311d`
- `ole32!CoTaskMemFree` at `0x141ac33aa`
- `ole32!CoTaskMemFree` at `0x141ac3446`
- `USER32!SendMessageW` at `0x141ac2da6`
- `USER32!SendMessageW` at `0x141ac3179`
- `USER32!SendMessageW` at `0x141ac3413`
- `USER32!SendMessageW` at `0x141ac34a2`
- `USER32!SendMessageW` at `0x141ac3792`
- `USER32!SendMessageW` at `0x141ac2da6`
- `USER32!SendMessageW` at `0x141ac3179`
- `USER32!SendMessageW` at `0x141ac3413`
- `USER32!SendMessageW` at `0x141ac34a2`
- `USER32!SendMessageW` at `0x141ac3792`
- `USER32!SendDlgItemMessageA` at `0x141ac2dc3`
- `USER32!SendDlgItemMessageA` at `0x141ac3141`
- `USER32!SendDlgItemMessageA` at `0x141ac33db`
- `USER32!SendDlgItemMessageA` at `0x141ac3430`
- `USER32!SendDlgItemMessageA` at `0x141ac346a`
- `USER32!SendDlgItemMessageA` at `0x141ac3676`
- `USER32!SendDlgItemMessageA` at `0x141ac36ee`
- `USER32!SendDlgItemMessageA` at `0x141ac2dc3`
- `USER32!SendDlgItemMessageA` at `0x141ac3141`
- `USER32!SendDlgItemMessageA` at `0x141ac33db`
- `USER32!SendDlgItemMessageA` at `0x141ac3430`
- `USER32!SendDlgItemMessageA` at `0x141ac346a`
- `USER32!SendDlgItemMessageA` at `0x141ac3676`
- `USER32!SendDlgItemMessageA` at `0x141ac36ee`
- `USER32!GetDlgItem` at `0x141ac2d6e`
- `USER32!GetDlgItem` at `0x141ac30df`
- `USER32!GetDlgItem` at `0x141ac375e`
- `USER32!GetDlgItem` at `0x141ac37d1`
- `USER32!GetDlgItem` at `0x141ac2d6e`
- `USER32!GetDlgItem` at `0x141ac30df`
- `USER32!GetDlgItem` at `0x141ac375e`
- `USER32!GetDlgItem` at `0x141ac37d1`
- `USER32!SendMessageA` at `0x141ac37e6`
- `USER32!SendMessageA` at `0x141ac37e6`
- `Mso98Win32Client!__imp_?MsoCreateFileW@Monitoring@FileIO@@YAPEAXPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z` at `0x141ac2df0`
- `Mso98Win32Client!__imp_?MsoCreateFileW@Monitoring@FileIO@@YAPEAXPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z` at `0x141ac2df0`
- `Mso20Win32Client!__imp_?MsoFRegKeyExists@@YAHPEBU_msoreg@@@Z` at `0x141ac36ca`
- `Mso20Win32Client!__imp_?MsoFRegKeyExists@@YAHPEBU_msoreg@@@Z` at `0x141ac36ca`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x141ac2e5c`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x141ac2e6c`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x141ac34b1`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x141ac34c5`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x141ac37a5`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x141ac2e5c`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x141ac2e6c`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x141ac34b1`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x141ac34c5`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x141ac37a5`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x141ac2d1f`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x141ac3375`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x141ac2d1f`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x141ac3375`

## pseudocode

```c

```
