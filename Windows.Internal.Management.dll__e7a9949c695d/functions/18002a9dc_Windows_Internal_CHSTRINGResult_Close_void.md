# Windows::Internal::CHSTRINGResult::Close(void)

- ea: `0x18002a9dc`
- end: `0x18002aa2f`
- name: `?Close@CHSTRINGResult@Internal@Windows@@QEAAXXZ`
- size: `83`
- prototype: `void __fastcall(Windows::Internal::CHSTRINGResult *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180030d70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002a9f2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002a9f2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002aa10`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002aa10`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a9fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002a9fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002aa28`

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
0x18002a9dc  mov     [rsp+arg_0], rbx
0x18002a9e1  mov     [rsp+arg_8], rsi
0x18002a9e6  push    rdi
0x18002a9e7  sub     rsp, 20h
0x18002a9eb  mov     rsi, rcx
0x18002a9ee  add     rcx, 18h; SRWLock
0x18002a9f2  call    cs:__imp_AcquireSRWLockExclusive
0x18002a9f8  xor     ecx, ecx; string
0x18002a9fa  call    cs:__imp_WindowsDeleteString
0x18002aa00  mov     rbx, [rsi+10h]
0x18002aa04  lea     rcx, [rsi+18h]; SRWLock
0x18002aa08  mov     qword ptr [rsi+10h], 0
0x18002aa10  call    cs:__imp_ReleaseSRWLockExclusive
0x18002aa16  mov     rcx, rbx
0x18002aa19  mov     rbx, [rsp+28h+arg_0]
0x18002aa1e  mov     rsi, [rsp+28h+arg_8]
0x18002aa23  add     rsp, 20h
0x18002aa27  pop     rdi
0x18002aa28  jmp     cs:__imp_WindowsDeleteString
```
