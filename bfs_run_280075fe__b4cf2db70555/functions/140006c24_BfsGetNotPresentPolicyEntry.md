# BfsGetNotPresentPolicyEntry

- ea: `0x140006c24`
- end: `0x140006d18`
- name: `BfsGetNotPresentPolicyEntry`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1400055d8`

## callees

- `0x140001bc0`
- `0x140006c24`
- `0x140008ca8`
- `0x140012bc8`

## import_xrefs

- `ntoskrnl!RtlLengthSid` at `0x140006c4e`
- `ntoskrnl!RtlLengthSid` at `0x140006c6c`
- `ntoskrnl!RtlLengthSid` at `0x140006c4e`
- `ntoskrnl!RtlLengthSid` at `0x140006c6c`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140006cac`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140006cac`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140006ce7`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140006ce7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140006c9b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140006c9b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140006cf3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140006cf3`

## pseudocode

```c
__int64 __fastcall BfsGetNotPresentPolicyEntry(__int64 a1, void *a2, void *a3, PRTL_DYNAMIC_HASH_TABLE_ENTRY *a4)
{
  ULONG v8; // eax
  ULONG v9; // eax
  ULONG_PTR v10; // rbx
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v11; // rax
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v12; // rbx
  unsigned int v13; // edi
  __int64 result; // rax
  __int64 v15; // [rsp+40h] [rbp+8h] BYREF

  v15 = 0;
  v8 = RtlLengthSid(a2);
  BfsUpdateHash(a2, v8, &v15);
  v9 = RtlLengthSid(a3);
  BfsUpdateHash(a3, v9, &v15);
  v10 = BfsFinalHash(&v15);
  *a4 = 0;
  KeEnterCriticalRegion();
  ExAcquirePushLockSharedEx(a1, 0);
  v11 = BfsLookupPolicyEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 8), v10, a2, a3);
  v12 = v11;
  if ( v11 )
  {
    _InterlockedIncrement((volatile signed __int32 *)&v11[6]);
    v13 = 0;
  }
  else
  {
    v13 = -1072103391;
  }
  ExReleasePushLockSharedEx(a1, 0);
  KeLeaveCriticalRegion();
  result = v13;
  *a4 = v12;
  return result;
}

```

## disassembly

```asm
0x140006c24  mov     [rsp+arg_8], rbx
0x140006c29  mov     [rsp+arg_10], rbp
0x140006c2e  push    rsi
0x140006c2f  push    rdi
0x140006c30  push    r14
0x140006c32  sub     rsp, 20h
0x140006c36  mov     rbp, rcx
0x140006c39  mov     [rsp+38h+arg_0], 0
0x140006c42  mov     rcx, rdx; Sid
0x140006c45  mov     r14, r9
0x140006c48  mov     rdi, r8
0x140006c4b  mov     rsi, rdx
0x140006c4e  call    cs:__imp_RtlLengthSid
0x140006c55  nop     dword ptr [rax+rax+00h]
0x140006c5a  lea     r8, [rsp+38h+arg_0]
0x140006c5f  mov     rcx, rsi
0x140006c62  mov     edx, eax
0x140006c64  call    BfsUpdateHash
0x140006c69  mov     rcx, rdi; Sid
0x140006c6c  call    cs:__imp_RtlLengthSid
0x140006c73  nop     dword ptr [rax+rax+00h]
0x140006c78  lea     r8, [rsp+38h+arg_0]
0x140006c7d  mov     rcx, rdi
0x140006c80  mov     edx, eax
0x140006c82  call    BfsUpdateHash
0x140006c87  lea     rcx, [rsp+38h+arg_0]
0x140006c8c  call    BfsFinalHash
0x140006c91  mov     rbx, rax
0x140006c94  mov     qword ptr [r14], 0
0x140006c9b  call    cs:__imp_KeEnterCriticalRegion
0x140006ca2  nop     dword ptr [rax+rax+00h]
0x140006ca7  xor     edx, edx
0x140006ca9  mov     rcx, rbp
0x140006cac  call    cs:__imp_ExAcquirePushLockSharedEx
0x140006cb3  nop     dword ptr [rax+rax+00h]
0x140006cb8  mov     rcx, [rbp+8]; HashTable
0x140006cbc  mov     r9, rdi
0x140006cbf  mov     r8, rsi
0x140006cc2  mov     rdx, rbx
0x140006cc5  call    BfsLookupPolicyEntryHashTable
0x140006cca  mov     rbx, rax
0x140006ccd  test    rax, rax
0x140006cd0  jz      short loc_140006CDD
0x140006cd2  lock inc dword ptr [rax+90h]
0x140006cd9  xor     edi, edi
0x140006cdb  jmp     short loc_140006CE2
0x140006cdd  mov     edi, 0C0190021h
0x140006ce2  xor     edx, edx
0x140006ce4  mov     rcx, rbp
0x140006ce7  call    cs:__imp_ExReleasePushLockSharedEx
0x140006cee  nop     dword ptr [rax+rax+00h]
0x140006cf3  call    cs:__imp_KeLeaveCriticalRegion
0x140006cfa  nop     dword ptr [rax+rax+00h]
0x140006cff  mov     rbp, [rsp+38h+arg_10]
0x140006d04  mov     eax, edi
0x140006d06  mov     [r14], rbx
0x140006d09  mov     rbx, [rsp+38h+arg_8]
0x140006d0e  add     rsp, 20h
0x140006d12  pop     r14
0x140006d14  pop     rdi
0x140006d15  pop     rsi
0x140006d16  retn
```
