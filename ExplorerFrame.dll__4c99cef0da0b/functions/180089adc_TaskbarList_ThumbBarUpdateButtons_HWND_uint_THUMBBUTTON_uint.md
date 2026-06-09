# TaskbarList::_ThumbBarUpdateButtons(HWND__ *,uint,THUMBBUTTON *,uint)

- ea: `0x180089adc`
- end: `0x180089d4a`
- name: `?_ThumbBarUpdateButtons@TaskbarList@@IEAAJPEAUHWND__@@IPEAUTHUMBBUTTON@@I@Z`
- size: `622`
- prototype: `__int64 __fastcall(TaskbarList *__hidden this, HWND, unsigned int, struct THUMBBUTTON *, UINT Msg)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task, installer_update`

## callers

- `0x180088010`
- `0x180089ac0`

## callees

- `0x1800899cc`
- `0x180089adc`
- `0x180089d70`

## import_xrefs

- `SHCORE!__imp_SHAllocShared` at `0x180089b4d`
- `SHCORE!__imp_SHAllocShared` at `0x180089b4d`
- `SHCORE!__imp_SHLockSharedEx` at `0x180089b6f`
- `SHCORE!__imp_SHLockSharedEx` at `0x180089cc8`
- `SHCORE!__imp_SHLockSharedEx` at `0x180089b6f`
- `SHCORE!__imp_SHLockSharedEx` at `0x180089cc8`
- `SHCORE!__imp_SHUnlockShared` at `0x180089c69`
- `SHCORE!__imp_SHUnlockShared` at `0x180089cfb`
- `SHCORE!__imp_SHUnlockShared` at `0x180089c69`
- `SHCORE!__imp_SHUnlockShared` at `0x180089cfb`
- `SHCORE!__imp_SHFreeShared` at `0x180089d0b`
- `SHCORE!__imp_SHFreeShared` at `0x180089d0b`
- `USER32!CopyIcon` at `0x180089c48`
- `USER32!CopyIcon` at `0x180089c48`
- `USER32!SendMessageTimeoutW` at `0x180089ca7`
- `USER32!SendMessageTimeoutW` at `0x180089ca7`
- `USER32!GetWindowThreadProcessId` at `0x180089b34`
- `USER32!GetWindowThreadProcessId` at `0x180089b34`
- `USER32!DestroyIcon` at `0x180089d39`
- `USER32!DestroyIcon` at `0x180089d39`

## pseudocode

```c

```
