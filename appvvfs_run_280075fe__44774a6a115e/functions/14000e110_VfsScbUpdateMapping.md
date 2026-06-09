# VfsScbUpdateMapping

- ea: `0x14000e110`
- end: `0x14000e183`
- name: `VfsScbUpdateMapping`
- size: `115`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14000c6fc`
- `0x14000c8c4`

## callees

- `0x140009368`
- `0x14000e110`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x14000e159`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000e159`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000e12b`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000e12b`

## pseudocode

```c
void __fastcall VfsScbUpdateMapping(__int64 a1, volatile signed __int32 *a2)
{
  volatile signed __int32 *v4; // rdi
  volatile signed __int32 *v5; // rax

  v4 = 0;
  ExAcquireFastMutex(*(PFAST_MUTEX *)(a1 + 120));
  v5 = *(volatile signed __int32 **)(a1 + 144);
  if ( a2 != v5 )
  {
    *(_QWORD *)(a1 + 144) = a2;
    v4 = v5;
    if ( a2 )
      _InterlockedIncrement(a2);
  }
  ExReleaseFastMutex(*(PFAST_MUTEX *)(a1 + 120));
  if ( v4 )
    VfsReleaseMappingEntry((PVOID)v4);
}

```

## disassembly

```asm
0x14000e110  mov     [rsp+arg_0], rbx
0x14000e115  mov     [rsp+arg_8], rsi
0x14000e11a  push    rdi
0x14000e11b  sub     rsp, 20h
0x14000e11f  mov     rsi, rcx
0x14000e122  mov     rbx, rdx
0x14000e125  mov     rcx, [rcx+78h]; FastMutex
0x14000e129  xor     edi, edi
0x14000e12b  call    cs:__imp_ExAcquireFastMutex
0x14000e132  nop     dword ptr [rax+rax+00h]
0x14000e137  mov     rax, [rsi+90h]
0x14000e13e  cmp     rbx, rax
0x14000e141  jz      short loc_14000E155
0x14000e143  mov     [rsi+90h], rbx
0x14000e14a  mov     rdi, rax
0x14000e14d  test    rbx, rbx
0x14000e150  jz      short loc_14000E155
0x14000e152  lock inc dword ptr [rbx]
0x14000e155  mov     rcx, [rsi+78h]; FastMutex
0x14000e159  call    cs:__imp_ExReleaseFastMutex
0x14000e160  nop     dword ptr [rax+rax+00h]
0x14000e165  test    rdi, rdi
0x14000e168  jz      short loc_14000E172
0x14000e16a  mov     rcx, rdi; P
0x14000e16d  call    VfsReleaseMappingEntry
0x14000e172  mov     rbx, [rsp+28h+arg_0]
0x14000e177  mov     rsi, [rsp+28h+arg_8]
0x14000e17c  add     rsp, 20h
0x14000e180  pop     rdi
0x14000e181  retn
```
