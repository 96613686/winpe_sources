# ConnectedStorage::UserManager::LocalUserInfo::~LocalUserInfo(void)

- ea: `0x180029e38`
- end: `0x180029e7d`
- name: `??1LocalUserInfo@UserManager@ConnectedStorage@@QEAA@XZ`
- size: `69`
- prototype: `void __fastcall(ConnectedStorage::UserManager::LocalUserInfo *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180028b4c`
- `0x18002b5b0`
- `0x18002da8c`
- `0x18002e268`
- `0x1800876f2`
- `0x1800879ce`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029e45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029e57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029e69`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029e45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029e57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029e69`

## pseudocode

```c
void __fastcall ConnectedStorage::UserManager::LocalUserInfo::~LocalUserInfo(HSTRING *this)
{
  WindowsDeleteString(this[3]);
  this[3] = 0;
  WindowsDeleteString(this[2]);
  this[2] = 0;
  WindowsDeleteString(this[1]);
  this[1] = 0;
}

```

## disassembly

```asm
0x180029e38  push    rbx
0x180029e3a  sub     rsp, 20h
0x180029e3e  mov     rbx, rcx
0x180029e41  mov     rcx, [rcx+18h]; string
0x180029e45  call    cs:__imp_WindowsDeleteString
0x180029e4b  mov     qword ptr [rbx+18h], 0
0x180029e53  mov     rcx, [rbx+10h]; string
0x180029e57  call    cs:__imp_WindowsDeleteString
0x180029e5d  mov     qword ptr [rbx+10h], 0
0x180029e65  mov     rcx, [rbx+8]; string
0x180029e69  call    cs:__imp_WindowsDeleteString
0x180029e6f  mov     qword ptr [rbx+8], 0
0x180029e77  add     rsp, 20h
0x180029e7b  pop     rbx
0x180029e7c  retn
```
