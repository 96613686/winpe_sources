# UIItemsView::WndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x1800b8640`
- end: `0x1800b8e7f`
- name: `?WndProc@UIItemsView@@UEAA_JPEAUHWND__@@I_K_J@Z`
- size: `2111`
- prototype: `__int64 __usercall@<rax>(UIItemsView *__hidden this@<rcx>, HWND hWnd@<rdx>, unsigned int@<r8d>, unsigned __int64@<r9>, __int64)`
- caller_count: `0`
- callee_count: `38`
- tags: `installer_update`

## callees

- `0x180015640`
- `0x180015fe0`
- `0x1800167c0`
- `0x18001b8d0`
- `0x18001c560`
- `0x180020fa0`
- `0x180021070`
- `0x180057ae4`
- `0x1800599fc`
- `0x180059f94`
- `0x180066910`
- `0x180079b34`
- `0x18007b4e8`
- `0x18008a204`
- `0x18009f24c`
- `0x1800b0290`
- `0x1800b4c18`
- `0x1800b8640`
- `0x1800b8e88`
- `0x1800b911c`
- `0x1800d191c`
- `0x1800d8c28`
- `0x1800f5320`
- `0x1800f733c`
- `0x180104ab0`
- `0x18010a0d8`
- `0x180125248`
- `0x18012f1b8`
- `0x18012fb80`
- `0x180130024`
- `0x180130a48`
- `0x1801e56ec`
- `0x1801e573c`
- `0x1801e5818`
- `0x1801e5924`
- `0x1801f2660`
- `0x1801f2b54`
- `0x180210010`

## import_xrefs

- `USER32!UpdateWindow` at `0x1800b8dbe`
- `USER32!UpdateWindow` at `0x1800b8dbe`
- `USER32!CloseGestureInfoHandle` at `0x1800b8c0e`
- `USER32!CloseGestureInfoHandle` at `0x1800b8c0e`
- `USER32!GetGestureInfo` at `0x1800b8bdf`
- `USER32!GetGestureInfo` at `0x1800b8bdf`
- `USER32!DefWindowProcW` at `0x1800b88f6`
- `USER32!DefWindowProcW` at `0x1800b88f6`
- `USER32!GetKeyState` at `0x1800b8ac5`
- `USER32!GetKeyState` at `0x1800b8afd`
- `USER32!GetKeyState` at `0x1800b8ac5`
- `USER32!GetKeyState` at `0x1800b8afd`
- `USER32!KillTimer` at `0x1800b884a`
- `USER32!KillTimer` at `0x1800b8c5d`
- `USER32!KillTimer` at `0x1800b884a`
- `USER32!KillTimer` at `0x1800b8c5d`
- `USER32!GetCursorPos` at `0x1800b892d`
- `USER32!GetCursorPos` at `0x1800b892d`
- `USER32!ScreenToClient` at `0x1800b894c`
- `USER32!ScreenToClient` at `0x1800b894c`
- `USER32!RedrawWindow` at `0x1800b8a3b`
- `USER32!RedrawWindow` at `0x1800b8a3b`
- `USER32!GetWindowLongPtrW` at `0x1800b8a4e`
- `USER32!GetWindowLongPtrW` at `0x1800b8a4e`
- `USER32!ClientToScreen` at `0x1800b88d1`
- `USER32!ClientToScreen` at `0x1800b88d1`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x1800b8a6d`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x1800b8a6d`
- `DUI70!?SetHeight@Element@DirectUI@@QEAAJH@Z` at `0x1800b8a8e`
- `DUI70!?SetHeight@Element@DirectUI@@QEAAJH@Z` at `0x1800b8a8e`
- `DUI70!?SetWidth@Element@DirectUI@@QEAAJH@Z` at `0x1800b8a7b`
- `DUI70!?SetWidth@Element@DirectUI@@QEAAJH@Z` at `0x1800b8a7b`
- `DUI70!?GetParent@Element@DirectUI@@QEAAPEAV12@XZ` at `0x1800b87d6`
- `DUI70!?GetParent@Element@DirectUI@@QEAAPEAV12@XZ` at `0x1800b87d6`
- `DUI70!?BroadcastEvent@Element@DirectUI@@QEAAXPEAUEvent@2@@Z` at `0x1800b8ca8`
- `DUI70!?BroadcastEvent@Element@DirectUI@@QEAAXPEAUEvent@2@@Z` at `0x1800b8ca8`
- `DUI70!?GetActive@Element@DirectUI@@QEAAHXZ` at `0x1800b87eb`
- `DUI70!?GetActive@Element@DirectUI@@QEAAHXZ` at `0x1800b87eb`
- `DUI70!?GetKeyWithin@Element@DirectUI@@QEAA_NXZ` at `0x1800b8865`
- `DUI70!?GetKeyWithin@Element@DirectUI@@QEAA_NXZ` at `0x1800b8aa4`
- `DUI70!?GetKeyWithin@Element@DirectUI@@QEAA_NXZ` at `0x1800b8865`
- `DUI70!?GetKeyWithin@Element@DirectUI@@QEAA_NXZ` at `0x1800b8aa4`
- `DUI70!?ElementFromPoint@HWNDElement@DirectUI@@QEAAPEAVElement@2@PEAUtagPOINT@@@Z` at `0x1800b8959`
- `DUI70!?ElementFromPoint@HWNDElement@DirectUI@@QEAAPEAVElement@2@PEAUtagPOINT@@@Z` at `0x1800b8959`
- `DUI70!?WndProc@HWNDElement@DirectUI@@UEAA_JPEAUHWND__@@I_K_J@Z` at `0x1800b86f7`
- `DUI70!?WndProc@HWNDElement@DirectUI@@UEAA_JPEAUHWND__@@I_K_J@Z` at `0x1800b8a12`
- `DUI70!?WndProc@HWNDElement@DirectUI@@UEAA_JPEAUHWND__@@I_K_J@Z` at `0x1800b86f7`
- `DUI70!?WndProc@HWNDElement@DirectUI@@UEAA_JPEAUHWND__@@I_K_J@Z` at `0x1800b8a12`

## pseudocode

```c

```
