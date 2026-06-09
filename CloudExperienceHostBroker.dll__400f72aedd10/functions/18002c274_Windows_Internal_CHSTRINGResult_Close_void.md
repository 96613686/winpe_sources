# Windows::Internal::CHSTRINGResult::Close(void)

- ea: `0x18002c274`
- end: `0x18002c2c7`
- name: `?Close@CHSTRINGResult@Internal@Windows@@QEAAXXZ`
- size: `83`
- prototype: `void __fastcall(Windows::Internal::CHSTRINGResult *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18002daa0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c2a8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c2a8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002c28a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002c28a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c292`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c292`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c2c0`

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
0x18002c274  mov     [rsp+arg_0], rbx
0x18002c279  mov     [rsp+arg_8], rsi
0x18002c27e  push    rdi
0x18002c27f  sub     rsp, 20h
0x18002c283  mov     rsi, rcx
0x18002c286  add     rcx, 18h; SRWLock
0x18002c28a  call    cs:__imp_AcquireSRWLockExclusive
0x18002c290  xor     ecx, ecx; string
0x18002c292  call    cs:__imp_WindowsDeleteString
0x18002c298  mov     rbx, [rsi+10h]
0x18002c29c  lea     rcx, [rsi+18h]; SRWLock
0x18002c2a0  mov     qword ptr [rsi+10h], 0
0x18002c2a8  call    cs:__imp_ReleaseSRWLockExclusive
0x18002c2ae  mov     rcx, rbx
0x18002c2b1  mov     rbx, [rsp+28h+arg_0]
0x18002c2b6  mov     rsi, [rsp+28h+arg_8]
0x18002c2bb  add     rsp, 20h
0x18002c2bf  pop     rdi
0x18002c2c0  jmp     cs:__imp_WindowsDeleteString
```
