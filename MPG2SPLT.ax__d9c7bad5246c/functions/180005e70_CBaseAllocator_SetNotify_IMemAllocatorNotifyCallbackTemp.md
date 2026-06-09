# CBaseAllocator::SetNotify(IMemAllocatorNotifyCallbackTemp *)

- ea: `0x180005e70`
- end: `0x180005ee7`
- name: `?SetNotify@CBaseAllocator@@UEAAJPEAUIMemAllocatorNotifyCallbackTemp@@@Z`
- size: `119`
- prototype: `__int64 __fastcall(CBaseAllocator *__hidden this, struct IMemAllocatorNotifyCallbackTemp *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180005e70`
- `0x180034010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180005ecf`
- `KERNEL32!LeaveCriticalSection` at `0x180005ecf`
- `KERNEL32!EnterCriticalSection` at `0x180005e99`
- `KERNEL32!EnterCriticalSection` at `0x180005e99`

## pseudocode

```c
__int64 __fastcall CBaseAllocator::SetNotify(CBaseAllocator *this, struct IMemAllocatorNotifyCallbackTemp *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rsi
  __int64 v5; // rcx

  v4 = (struct _RTL_CRITICAL_SECTION *)(((unsigned __int64)this + 8) & -(__int64)(this != (CBaseAllocator *)24));
  EnterCriticalSection(v4);
  if ( a2 )
    ((void (__fastcall *)(struct IMemAllocatorNotifyCallbackTemp *))a2->lpVtbl->AddRef)(a2);
  v5 = *((_QWORD *)this + 14);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  *((_QWORD *)this + 14) = a2;
  LeaveCriticalSection(v4);
  return 0;
}

```

## disassembly

```asm
0x180005e70  mov     [rsp+arg_0], rbx
0x180005e75  mov     [rsp+arg_8], rsi
0x180005e7a  push    rdi
0x180005e7b  sub     rsp, 20h
0x180005e7f  lea     rax, [rcx-18h]
0x180005e83  mov     rbx, rcx
0x180005e86  lea     r8, [rcx+8]
0x180005e8a  neg     rax
0x180005e8d  mov     rdi, rdx
0x180005e90  sbb     rsi, rsi
0x180005e93  and     rsi, r8
0x180005e96  mov     rcx, rsi; lpCriticalSection
0x180005e99  call    cs:__imp_EnterCriticalSection
0x180005e9f  test    rdi, rdi
0x180005ea2  jz      short loc_180005EB3
0x180005ea4  mov     rax, [rdi]
0x180005ea7  mov     rcx, rdi
0x180005eaa  mov     rax, [rax+8]
0x180005eae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005eb3  mov     rcx, [rbx+70h]
0x180005eb7  test    rcx, rcx
0x180005eba  jz      short loc_180005EC8
0x180005ebc  mov     rax, [rcx]
0x180005ebf  mov     rax, [rax+10h]
0x180005ec3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ec8  mov     rcx, rsi; lpCriticalSection
0x180005ecb  mov     [rbx+70h], rdi
0x180005ecf  call    cs:__imp_LeaveCriticalSection
0x180005ed5  mov     rbx, [rsp+28h+arg_0]
0x180005eda  xor     eax, eax
0x180005edc  mov     rsi, [rsp+28h+arg_8]
0x180005ee1  add     rsp, 20h
0x180005ee5  pop     rdi
0x180005ee6  retn
```
