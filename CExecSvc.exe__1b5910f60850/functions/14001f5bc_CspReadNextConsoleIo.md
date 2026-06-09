# CspReadNextConsoleIo

- ea: `0x14001f5bc`
- end: `0x14001f6b1`
- name: `CspReadNextConsoleIo`
- size: `245`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140016cc0`
- `0x14001f0e0`

## callees

- `0x14001f5bc`
- `0x14001f754`
- `0x140024010`

## import_xrefs

- `ntdll!RtlAcquireSRWLockShared` at `0x14001f5d5`
- `ntdll!RtlAcquireSRWLockShared` at `0x14001f5d5`
- `ntdll!RtlReleaseSRWLockShared` at `0x14001f67f`
- `ntdll!RtlReleaseSRWLockShared` at `0x14001f69b`
- `ntdll!RtlReleaseSRWLockShared` at `0x14001f67f`
- `ntdll!RtlReleaseSRWLockShared` at `0x14001f69b`
- `ntdll!NtDeviceIoControlFile` at `0x14001f653`
- `ntdll!NtDeviceIoControlFile` at `0x14001f653`
- `ntdll!TpCancelAsyncIoOperation` at `0x14001f663`
- `ntdll!TpCancelAsyncIoOperation` at `0x14001f663`
- `ntdll!TpStartAsyncIoOperation` at `0x14001f602`
- `ntdll!TpStartAsyncIoOperation` at `0x14001f602`

## pseudocode

```c
__int64 __fastcall CspReadNextConsoleIo(__int64 a1)
{
  __int64 v1; // rdi
  NTSTATUS v3; // esi

  v1 = a1 + 48;
  RtlAcquireSRWLockShared(a1 + 48);
  if ( *(_QWORD *)(a1 + 208) )
    ReleaseMessageBuffers(a1, a1 + 216);
  if ( *(_BYTE *)(a1 + 56) )
    return RtlReleaseSRWLockShared(v1);
  TpStartAsyncIoOperation(*(_QWORD *)(a1 + 24));
  v3 = NtDeviceIoControlFile(
         *(HANDLE *)a1,
         0,
         0,
         (PVOID)(a1 + 296),
         (PIO_STATUS_BLOCK)(a1 + 296),
         0x500006u,
         *(PVOID *)(a1 + 208),
         *(_QWORD *)(a1 + 208) != 0 ? 0x28 : 0,
         (PVOID)(a1 + 312),
         0x68u);
  if ( v3 >= 0 )
    return RtlReleaseSRWLockShared(v1);
  TpCancelAsyncIoOperation(*(_QWORD *)(a1 + 24));
  if ( v3 != -1073741648 || !*(_QWORD *)(*(_QWORD *)(a1 + 32) + 16LL) )
    return RtlReleaseSRWLockShared(v1);
  RtlReleaseSRWLockShared(v1);
  return (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)(a1 + 32) + 16LL))(*(_QWORD *)(a1 + 16));
}

```

## disassembly

```asm
0x14001f5bc  mov     [rsp+arg_0], rbx
0x14001f5c1  mov     [rsp+arg_8], rsi
0x14001f5c6  push    rdi
0x14001f5c7  sub     rsp, 50h
0x14001f5cb  lea     rdi, [rcx+30h]
0x14001f5cf  mov     rbx, rcx
0x14001f5d2  mov     rcx, rdi
0x14001f5d5  call    cs:__imp_RtlAcquireSRWLockShared
0x14001f5db  cmp     qword ptr [rbx+0D0h], 0
0x14001f5e3  jz      short loc_14001F5F4
0x14001f5e5  lea     rdx, [rbx+0D8h]
0x14001f5ec  mov     rcx, rbx
0x14001f5ef  call    ReleaseMessageBuffers
0x14001f5f4  cmp     byte ptr [rbx+38h], 0
0x14001f5f8  jnz     loc_14001F698
0x14001f5fe  mov     rcx, [rbx+18h]
0x14001f602  call    cs:__imp_TpStartAsyncIoOperation
0x14001f608  mov     r8, [rbx+0D0h]
0x14001f60f  lea     rdx, [rbx+138h]
0x14001f616  mov     [rsp+58h+OutputBufferLength], 68h ; 'h'; OutputBufferLength
0x14001f61e  lea     r9, [rbx+128h]; ApcContext
0x14001f625  mov     [rsp+58h+OutputBuffer], rdx; OutputBuffer
0x14001f62a  mov     rax, r8
0x14001f62d  neg     rax
0x14001f630  sbb     ecx, ecx
0x14001f632  xor     edx, edx; Event
0x14001f634  and     ecx, 28h
0x14001f637  mov     [rsp+58h+InputBufferLength], ecx; InputBufferLength
0x14001f63b  mov     rcx, [rbx]; FileHandle
0x14001f63e  mov     [rsp+58h+InputBuffer], r8; InputBuffer
0x14001f643  xor     r8d, r8d; ApcRoutine
0x14001f646  mov     [rsp+58h+IoControlCode], 500006h; IoControlCode
0x14001f64e  mov     [rsp+58h+IoStatusBlock], r9; IoStatusBlock
0x14001f653  call    cs:__imp_NtDeviceIoControlFile
0x14001f659  mov     esi, eax
0x14001f65b  test    eax, eax
0x14001f65d  jns     short loc_14001F698
0x14001f65f  mov     rcx, [rbx+18h]
0x14001f663  call    cs:__imp_TpCancelAsyncIoOperation
0x14001f669  cmp     esi, 0C00000B0h
0x14001f66f  jnz     short loc_14001F698
0x14001f671  mov     rax, [rbx+20h]
0x14001f675  cmp     qword ptr [rax+10h], 0
0x14001f67a  jz      short loc_14001F698
0x14001f67c  mov     rcx, rdi
0x14001f67f  call    cs:__imp_RtlReleaseSRWLockShared
0x14001f685  mov     rax, [rbx+20h]
0x14001f689  mov     rcx, [rbx+10h]
0x14001f68d  mov     rax, [rax+10h]
0x14001f691  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f696  jmp     short loc_14001F6A1
0x14001f698  mov     rcx, rdi
0x14001f69b  call    cs:__imp_RtlReleaseSRWLockShared
0x14001f6a1  mov     rbx, [rsp+58h+arg_0]
0x14001f6a6  mov     rsi, [rsp+58h+arg_8]
0x14001f6ab  add     rsp, 50h
0x14001f6af  pop     rdi
0x14001f6b0  retn
```
