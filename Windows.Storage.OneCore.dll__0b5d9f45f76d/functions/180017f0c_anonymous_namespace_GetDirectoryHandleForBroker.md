# _anonymous_namespace_::GetDirectoryHandleForBroker

- ea: `0x180017f0c`
- end: `0x180017f6a`
- name: `_anonymous_namespace_::GetDirectoryHandleForBroker`
- size: `94`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180017c60`

## callees

- `0x180017f0c`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x180017f3e`
- `ntdll!RtlDeleteCriticalSection` at `0x180017f3e`
- `ntdll!RtlFreeHeap` at `0x180017f34`
- `ntdll!RtlFreeHeap` at `0x180017f56`
- `ntdll!RtlFreeHeap` at `0x180017f34`
- `ntdll!RtlFreeHeap` at `0x180017f56`

## pseudocode

```c
PRTL_CRITICAL_SECTION_DEBUG __fastcall anonymous_namespace_::GetDirectoryHandleForBroker(
        struct _RTL_CRITICAL_SECTION *P)
{
  void *v1; // r8
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rdi

  v1 = *(void **)&P->LockCount;
  DebugInfo = P->DebugInfo;
  if ( v1 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v1);
  RtlDeleteCriticalSection(P + 1);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  return DebugInfo;
}

```

## disassembly

```asm
0x180017f0c  mov     [rsp+arg_0], rbx
0x180017f11  push    rdi
0x180017f12  sub     rsp, 20h
0x180017f16  mov     r8, [rcx+8]; P
0x180017f1a  mov     rbx, rcx
0x180017f1d  mov     rdi, [rcx]
0x180017f20  test    r8, r8
0x180017f23  jz      short loc_180017F3A
0x180017f25  mov     rcx, gs:60h
0x180017f2e  xor     edx, edx; Flags
0x180017f30  mov     rcx, [rcx+30h]; HeapHandle
0x180017f34  call    cs:__imp_RtlFreeHeap
0x180017f3a  lea     rcx, [rbx+28h]; CriticalSection
0x180017f3e  call    cs:__imp_RtlDeleteCriticalSection
0x180017f44  mov     rcx, gs:60h
0x180017f4d  mov     r8, rbx; P
0x180017f50  xor     edx, edx; Flags
0x180017f52  mov     rcx, [rcx+30h]; HeapHandle
0x180017f56  call    cs:__imp_RtlFreeHeap
0x180017f5c  mov     rbx, [rsp+28h+arg_0]
0x180017f61  mov     rax, rdi
0x180017f64  add     rsp, 20h
0x180017f68  pop     rdi
0x180017f69  retn
```
