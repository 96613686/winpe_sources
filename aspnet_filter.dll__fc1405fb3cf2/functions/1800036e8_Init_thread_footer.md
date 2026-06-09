# _Init_thread_footer

- ea: `0x1800036e8`
- end: `0x180003748`
- name: `_Init_thread_footer`
- size: `96`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800014a0`

## callees

- `0x1800037b0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180003738`
- `KERNEL32!LeaveCriticalSection` at `0x180003738`
- `KERNEL32!EnterCriticalSection` at `0x1800036f8`
- `KERNEL32!EnterCriticalSection` at `0x1800036f8`

## pseudocode

```c
int __fastcall Init_thread_footer(_DWORD *a1)
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
0x1800036e8  push    rbx
0x1800036ea  sub     rsp, 20h
0x1800036ee  mov     rbx, rcx
0x1800036f1  lea     rcx, CriticalSection; lpCriticalSection
0x1800036f8  call    cs:__imp_EnterCriticalSection
0x1800036fe  mov     eax, cs:_Init_global_epoch
0x180003704  lea     rcx, CriticalSection; lpCriticalSection
0x18000370b  mov     edx, cs:_tls_index
0x180003711  inc     eax
0x180003713  mov     cs:_Init_global_epoch, eax
0x180003719  mov     [rbx], eax
0x18000371b  mov     rax, gs:58h
0x180003724  mov     r9d, 4
0x18000372a  mov     r8, [rax+rdx*8]
0x18000372e  mov     eax, cs:_Init_global_epoch
0x180003734  mov     [r9+r8], eax
0x180003738  call    cs:__imp_LeaveCriticalSection
0x18000373e  add     rsp, 20h
0x180003742  pop     rbx
0x180003743  jmp     _Init_thread_notify
```
