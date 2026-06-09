# Windows::Internal::CHSTRINGResult::Close(void)

- ea: `0x180016b5c`
- end: `0x180016baf`
- name: `?Close@CHSTRINGResult@Internal@Windows@@QEAAXXZ`
- size: `83`
- prototype: `void __fastcall(RTL_SRWLOCK *this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180018810`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016b90`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016b90`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016b72`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016b72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016b7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016b7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180016ba8`

## pseudocode

```c
void __fastcall Windows::Internal::CHSTRINGResult::Close(RTL_SRWLOCK *this)
{
  HSTRING Ptr; // rbx

  AcquireSRWLockExclusive(this + 3);
  WindowsDeleteString(0);
  Ptr = (HSTRING)this[2].Ptr;
  this[2].Ptr = 0;
  ReleaseSRWLockExclusive(this + 3);
  WindowsDeleteString(Ptr);
}

```

## disassembly

```asm
0x180016b5c  mov     [rsp+arg_0], rbx
0x180016b61  mov     [rsp+arg_8], rsi
0x180016b66  push    rdi
0x180016b67  sub     rsp, 20h
0x180016b6b  mov     rsi, rcx
0x180016b6e  add     rcx, 18h; SRWLock
0x180016b72  call    cs:__imp_AcquireSRWLockExclusive
0x180016b78  xor     ecx, ecx; string
0x180016b7a  call    cs:__imp_WindowsDeleteString
0x180016b80  mov     rbx, [rsi+10h]
0x180016b84  lea     rcx, [rsi+18h]; SRWLock
0x180016b88  mov     qword ptr [rsi+10h], 0
0x180016b90  call    cs:__imp_ReleaseSRWLockExclusive
0x180016b96  mov     rcx, rbx
0x180016b99  mov     rbx, [rsp+28h+arg_0]
0x180016b9e  mov     rsi, [rsp+28h+arg_8]
0x180016ba3  add     rsp, 20h
0x180016ba7  pop     rdi
0x180016ba8  jmp     cs:__imp_WindowsDeleteString
```
