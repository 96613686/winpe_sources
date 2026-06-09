# Windows::Internal::CHSTRINGResult::Close(void)

- ea: `0x18009a0f0`
- end: `0x18009a143`
- name: `?Close@CHSTRINGResult@Internal@Windows@@QEAAXXZ`
- size: `83`
- prototype: `void __fastcall(Windows::Internal::CHSTRINGResult *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18009a740`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009a124`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18009a124`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18009a106`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18009a106`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009a10e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009a10e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009a13c`

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
0x18009a0f0  mov     [rsp+arg_0], rbx
0x18009a0f5  mov     [rsp+arg_8], rsi
0x18009a0fa  push    rdi
0x18009a0fb  sub     rsp, 20h
0x18009a0ff  mov     rsi, rcx
0x18009a102  add     rcx, 18h; SRWLock
0x18009a106  call    cs:__imp_AcquireSRWLockExclusive
0x18009a10c  xor     ecx, ecx; string
0x18009a10e  call    cs:__imp_WindowsDeleteString
0x18009a114  mov     rbx, [rsi+10h]
0x18009a118  lea     rcx, [rsi+18h]; SRWLock
0x18009a11c  mov     qword ptr [rsi+10h], 0
0x18009a124  call    cs:__imp_ReleaseSRWLockExclusive
0x18009a12a  mov     rcx, rbx
0x18009a12d  mov     rbx, [rsp+28h+arg_0]
0x18009a132  mov     rsi, [rsp+28h+arg_8]
0x18009a137  add     rsp, 20h
0x18009a13b  pop     rdi
0x18009a13c  jmp     cs:__imp_WindowsDeleteString
```
