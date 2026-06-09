# Windows::Internal::CHSTRINGResult::Close(void)

- ea: `0x180029334`
- end: `0x18002939e`
- name: `?Close@CHSTRINGResult@Internal@Windows@@QEAAXXZ`
- size: `106`
- prototype: `void __fastcall(Windows::Internal::CHSTRINGResult *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18002f9f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180029374`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180029374`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002934a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002934a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029358`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029358`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029392`

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
0x180029334  mov     [rsp+arg_0], rbx
0x180029339  mov     [rsp+arg_8], rsi
0x18002933e  push    rdi
0x18002933f  sub     rsp, 20h
0x180029343  mov     rsi, rcx
0x180029346  add     rcx, 18h; SRWLock
0x18002934a  call    cs:__imp_AcquireSRWLockExclusive
0x180029351  nop     dword ptr [rax+rax+00h]
0x180029356  xor     ecx, ecx; string
0x180029358  call    cs:__imp_WindowsDeleteString
0x18002935f  nop     dword ptr [rax+rax+00h]
0x180029364  mov     rbx, [rsi+10h]
0x180029368  lea     rcx, [rsi+18h]; SRWLock
0x18002936c  mov     qword ptr [rsi+10h], 0
0x180029374  call    cs:__imp_ReleaseSRWLockExclusive
0x18002937b  nop     dword ptr [rax+rax+00h]
0x180029380  mov     rcx, rbx
0x180029383  mov     rbx, [rsp+28h+arg_0]
0x180029388  mov     rsi, [rsp+28h+arg_8]
0x18002938d  add     rsp, 20h
0x180029391  pop     rdi
0x180029392  jmp     cs:__imp_WindowsDeleteString
```
