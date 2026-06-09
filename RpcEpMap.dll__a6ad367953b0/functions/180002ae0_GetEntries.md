# GetEntries

- ea: `0x180002ae0`
- end: `0x180002bb8`
- name: `GetEntries`
- size: `216`
- prototype: `__int64 __fastcall(__int64, __int64, int, __int64, __int64, __int64 *, __int64, int, unsigned int, unsigned int, unsigned int *, int, int, __int64, _DWORD *)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001100`
- `0x1800023a8`
- `0x180003a1c`

## callees

- `0x180002bc0`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x180002ba4`
- `ntdll!RtlReleaseSRWLockShared` at `0x180002ba4`
- `ntdll!RtlAcquireSRWLockShared` at `0x180002aff`
- `ntdll!RtlAcquireSRWLockShared` at `0x180002aff`

## pseudocode

```c
__int64 __fastcall GetEntries(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        void *a5,
        __int64 *a6,
        _QWORD *a7,
        int a8,
        unsigned int a9,
        unsigned int a10,
        unsigned int *a11,
        int a12,
        int a13,
        unsigned int (__fastcall *a14)(__int64 *, __int64, __int64, _QWORD, int, int),
        _DWORD *a15)
{
  RtlAcquireSRWLockShared(&EpMapRWLock);
  LODWORD(a4) = GetEntriesNoLock(a1, a2, a3, a4, a5, a6, a7, a8, a9, a10, a11, a12, a13, a14, a15);
  RtlReleaseSRWLockShared(&EpMapRWLock);
  return (unsigned int)a4;
}

```

## disassembly

```asm
0x180002ae0  push    rbx
0x180002ae2  push    rbp
0x180002ae3  push    rsi
0x180002ae4  push    rdi
0x180002ae5  sub     rsp, 88h
0x180002aec  mov     rbp, rcx
0x180002aef  mov     rbx, r9
0x180002af2  lea     rcx, ?EpMapRWLock@@3VRPC_SRWLOCK@@A; RPC_SRWLOCK EpMapRWLock
0x180002af9  mov     edi, r8d
0x180002afc  mov     rsi, rdx
0x180002aff  call    cs:__imp_RtlAcquireSRWLockShared
0x180002b05  mov     rax, [rsp+0A8h+arg_70]
0x180002b0d  mov     r9, rbx
0x180002b10  mov     [rsp+0A8h+var_38], rax
0x180002b15  mov     r8d, edi
0x180002b18  mov     rax, [rsp+0A8h+arg_68]
0x180002b20  mov     rdx, rsi
0x180002b23  mov     [rsp+0A8h+var_40], rax
0x180002b28  mov     rcx, rbp
0x180002b2b  mov     eax, [rsp+0A8h+arg_60]
0x180002b32  mov     [rsp+0A8h+var_48], eax
0x180002b36  mov     eax, [rsp+0A8h+arg_58]
0x180002b3d  mov     [rsp+0A8h+var_50], eax
0x180002b41  mov     rax, [rsp+0A8h+arg_50]
0x180002b49  mov     [rsp+0A8h+var_58], rax
0x180002b4e  mov     eax, [rsp+0A8h+arg_48]
0x180002b55  mov     [rsp+0A8h+var_60], eax
0x180002b59  mov     eax, [rsp+0A8h+arg_40]
0x180002b60  mov     [rsp+0A8h+var_68], eax
0x180002b64  mov     eax, [rsp+0A8h+arg_38]
0x180002b6b  mov     [rsp+0A8h+var_70], eax
0x180002b6f  mov     rax, [rsp+0A8h+arg_30]
0x180002b77  mov     [rsp+0A8h+var_78], rax
0x180002b7c  mov     rax, [rsp+0A8h+arg_28]
0x180002b84  mov     [rsp+0A8h+var_80], rax
0x180002b89  mov     rax, [rsp+0A8h+arg_20]
0x180002b91  mov     [rsp+0A8h+var_88], rax
0x180002b96  call    GetEntriesNoLock
0x180002b9b  lea     rcx, ?EpMapRWLock@@3VRPC_SRWLOCK@@A; RPC_SRWLOCK EpMapRWLock
0x180002ba2  mov     ebx, eax
0x180002ba4  call    cs:__imp_RtlReleaseSRWLockShared
0x180002baa  mov     eax, ebx
0x180002bac  add     rsp, 88h
0x180002bb3  pop     rdi
0x180002bb4  pop     rsi
0x180002bb5  pop     rbp
0x180002bb6  pop     rbx
0x180002bb7  retn
```
