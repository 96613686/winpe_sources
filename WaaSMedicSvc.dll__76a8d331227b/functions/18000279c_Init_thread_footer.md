# _Init_thread_footer

- ea: `0x18000279c`
- end: `0x1800027fc`
- name: `_Init_thread_footer`
- size: `96`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180009f58`
- `0x18000b900`
- `0x18000b9d0`
- `0x18000bac0`

## callees

- `0x180002870`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800027ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800027ec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800027ac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800027ac`

## pseudocode

```c
__int64 __fastcall Init_thread_footer(_DWORD *a1)
{
  __int64 v2; // rdx

  EnterCriticalSection(&CriticalSection);
  v2 = (unsigned int)tls_index;
  *a1 = ++Init_global_epoch;
  *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + v2) + 4LL) = Init_global_epoch;
  LeaveCriticalSection(&CriticalSection);
  return Init_thread_notify();
}

```

## disassembly

```asm
0x18000279c  push    rbx
0x18000279e  sub     rsp, 20h
0x1800027a2  mov     rbx, rcx
0x1800027a5  lea     rcx, CriticalSection; lpCriticalSection
0x1800027ac  call    cs:__imp_EnterCriticalSection
0x1800027b2  mov     eax, cs:_Init_global_epoch
0x1800027b8  lea     rcx, CriticalSection; lpCriticalSection
0x1800027bf  mov     edx, cs:_tls_index
0x1800027c5  inc     eax
0x1800027c7  mov     cs:_Init_global_epoch, eax
0x1800027cd  mov     [rbx], eax
0x1800027cf  mov     rax, gs:58h
0x1800027d8  mov     r9d, 4
0x1800027de  mov     r8, [rax+rdx*8]
0x1800027e2  mov     eax, cs:_Init_global_epoch
0x1800027e8  mov     [r9+r8], eax
0x1800027ec  call    cs:__imp_LeaveCriticalSection
0x1800027f2  add     rsp, 20h
0x1800027f6  pop     rbx
0x1800027f7  jmp     _Init_thread_notify
```
