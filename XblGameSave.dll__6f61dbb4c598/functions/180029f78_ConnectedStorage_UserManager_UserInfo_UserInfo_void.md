# ConnectedStorage::UserManager::UserInfo::~UserInfo(void)

- ea: `0x180029f78`
- end: `0x180029fc6`
- name: `??1UserInfo@UserManager@ConnectedStorage@@QEAA@XZ`
- size: `78`
- prototype: `void __fastcall(ConnectedStorage::UserManager::UserInfo *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180028b84`
- `0x18002d264`
- `0x18002e2f0`
- `0x18008795e`

## callees

- `0x18001c090`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029f8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029fa0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029fb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029f8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029fa0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029fb2`

## pseudocode

```c
void __fastcall ConnectedStorage::UserManager::UserInfo::~UserInfo(HSTRING *this)
{
  std::wstring::_Tidy_deallocate(this + 5);
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
0x180029f78  push    rbx
0x180029f7a  sub     rsp, 20h
0x180029f7e  mov     rbx, rcx
0x180029f81  add     rcx, 28h ; '('
0x180029f85  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029f8a  mov     rcx, [rbx+18h]; string
0x180029f8e  call    cs:__imp_WindowsDeleteString
0x180029f94  mov     qword ptr [rbx+18h], 0
0x180029f9c  mov     rcx, [rbx+10h]; string
0x180029fa0  call    cs:__imp_WindowsDeleteString
0x180029fa6  mov     qword ptr [rbx+10h], 0
0x180029fae  mov     rcx, [rbx+8]; string
0x180029fb2  call    cs:__imp_WindowsDeleteString
0x180029fb8  mov     qword ptr [rbx+8], 0
0x180029fc0  add     rsp, 20h
0x180029fc4  pop     rbx
0x180029fc5  retn
```
