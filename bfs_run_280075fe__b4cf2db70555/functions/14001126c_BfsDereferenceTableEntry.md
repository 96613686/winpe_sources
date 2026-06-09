# BfsDereferenceTableEntry

- ea: `0x14001126c`
- end: `0x140011348`
- name: `BfsDereferenceTableEntry`
- size: `220`
- prototype: `__int64 __fastcall(PVOID Buffer)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x1400061a0`
- `0x140006e14`
- `0x14001033c`
- `0x14001064c`
- `0x140010ffc`
- `0x140011b44`
- `0x140012478`

## callees

- `0x14001126c`
- `0x1400117fc`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400112a4`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400112a4`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140011314`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140011314`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1400112c5`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1400112c5`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400112d4`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400112d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400112e5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011303`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400112e5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011303`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140011293`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140011293`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140011320`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140011320`

## pseudocode

```c
void __fastcall BfsDereferenceTableEntry(volatile signed __int32 *Buffer)
{
  __int64 v2; // rbx
  __int64 v3; // rsi
  struct _UNICODE_STRING *v4; // rbx
  void *v5; // rbp

  do
  {
    if ( _InterlockedExchangeAdd(Buffer + 38, 0xFFFFFFFF) != 1 )
      break;
    v2 = *((_QWORD *)Buffer + 18);
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(v2, 0);
    v3 = *((_QWORD *)Buffer + 18);
    v4 = *(struct _UNICODE_STRING **)Buffer;
    v5 = (void *)*((_QWORD *)Buffer + 3);
    RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)(v3 + 32), (PVOID)Buffer);
    RtlFreeUnicodeString(v4);
    ExFreePoolWithTag(v4, 0);
    if ( v5 )
    {
      BfsFreeDirectoryBlockList(v5);
      ExFreePoolWithTag(v5, 0);
    }
    ExReleasePushLockExclusiveEx(v3, 0);
    KeLeaveCriticalRegion();
    Buffer = (volatile signed __int32 *)(v3 - 8);
  }
  while ( *(_QWORD *)(v3 - 8 + 144) );
}

```

## disassembly

```asm
0x14001126c  push    rbx
0x14001126e  push    rbp
0x14001126f  push    rsi
0x140011270  push    rdi
0x140011271  sub     rsp, 28h
0x140011275  mov     rdi, rcx
0x140011278  or      eax, 0FFFFFFFFh
0x14001127b  lock xadd [rdi+98h], eax
0x140011283  cmp     eax, 1
0x140011286  jnz     loc_14001133E
0x14001128c  mov     rbx, [rdi+90h]
0x140011293  call    cs:__imp_KeEnterCriticalRegion
0x14001129a  nop     dword ptr [rax+rax+00h]
0x14001129f  xor     edx, edx
0x1400112a1  mov     rcx, rbx
0x1400112a4  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400112ab  nop     dword ptr [rax+rax+00h]
0x1400112b0  mov     rsi, [rdi+90h]
0x1400112b7  mov     rdx, rdi; Buffer
0x1400112ba  mov     rbx, [rdi]
0x1400112bd  mov     rbp, [rdi+18h]
0x1400112c1  lea     rcx, [rsi+20h]; Table
0x1400112c5  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1400112cc  nop     dword ptr [rax+rax+00h]
0x1400112d1  mov     rcx, rbx; UnicodeString
0x1400112d4  call    cs:__imp_RtlFreeUnicodeString
0x1400112db  nop     dword ptr [rax+rax+00h]
0x1400112e0  xor     edx, edx; Tag
0x1400112e2  mov     rcx, rbx; P
0x1400112e5  call    cs:__imp_ExFreePoolWithTag
0x1400112ec  nop     dword ptr [rax+rax+00h]
0x1400112f1  test    rbp, rbp
0x1400112f4  jz      short loc_14001130F
0x1400112f6  mov     rcx, rbp
0x1400112f9  call    BfsFreeDirectoryBlockList
0x1400112fe  xor     edx, edx; Tag
0x140011300  mov     rcx, rbp; P
0x140011303  call    cs:__imp_ExFreePoolWithTag
0x14001130a  nop     dword ptr [rax+rax+00h]
0x14001130f  xor     edx, edx
0x140011311  mov     rcx, rsi
0x140011314  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14001131b  nop     dword ptr [rax+rax+00h]
0x140011320  call    cs:__imp_KeLeaveCriticalRegion
0x140011327  nop     dword ptr [rax+rax+00h]
0x14001132c  lea     rdi, [rsi-8]
0x140011330  cmp     qword ptr [rdi+90h], 0
0x140011338  jnz     loc_140011278
0x14001133e  add     rsp, 28h
0x140011342  pop     rdi
0x140011343  pop     rsi
0x140011344  pop     rbp
0x140011345  pop     rbx
0x140011346  retn
```
