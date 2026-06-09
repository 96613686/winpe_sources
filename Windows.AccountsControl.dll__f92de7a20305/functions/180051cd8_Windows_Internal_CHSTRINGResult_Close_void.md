# Windows::Internal::CHSTRINGResult::Close(void)

- ea: `0x180051cd8`
- end: `0x180051d3a`
- name: `?Close@CHSTRINGResult@Internal@Windows@@QEAAXXZ`
- size: `98`
- prototype: `void __fastcall(Windows::Internal::CHSTRINGResult *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180052a30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180051d1a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180051d1a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180051cf7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180051cf7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180051cff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180051cff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180051d33`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180051cd8  mov     [rsp+arg_8], rbx
0x180051cdd  mov     [rsp+arg_10], rsi
0x180051ce2  push    rdi
0x180051ce3  sub     rsp, 20h
0x180051ce7  mov     rsi, rcx
0x180051cea  mov     [rsp+28h+arg_0], 0
0x180051cf3  add     rcx, 18h; SRWLock
0x180051cf7  call    cs:__imp_AcquireSRWLockExclusive
0x180051cfd  xor     ecx, ecx; string
0x180051cff  call    cs:__imp_WindowsDeleteString
0x180051d05  mov     rbx, [rsi+10h]
0x180051d09  mov     [rsp+28h+arg_0], rbx
0x180051d0e  mov     qword ptr [rsi+10h], 0
0x180051d16  lea     rcx, [rsi+18h]; SRWLock
0x180051d1a  call    cs:__imp_ReleaseSRWLockExclusive
0x180051d20  nop
0x180051d21  mov     rcx, rbx
0x180051d24  mov     rbx, [rsp+28h+arg_8]
0x180051d29  mov     rsi, [rsp+28h+arg_10]
0x180051d2e  add     rsp, 20h
0x180051d32  pop     rdi
0x180051d33  jmp     cs:__imp_WindowsDeleteString
```
