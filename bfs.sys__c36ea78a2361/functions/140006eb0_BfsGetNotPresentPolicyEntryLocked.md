# BfsGetNotPresentPolicyEntryLocked

- ea: `0x140006eb0`
- end: `0x140006f53`
- name: `BfsGetNotPresentPolicyEntryLocked`
- size: `163`
- prototype: `__int64 __fastcall(__int64, void *, void *, PRTL_DYNAMIC_HASH_TABLE_ENTRY *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14000ed84`

## callees

- `0x1400017b0`
- `0x140006eb0`
- `0x140008e38`
- `0x140012d00`

## import_xrefs

- `ntoskrnl!RtlLengthSid` at `0x140006ed2`
- `ntoskrnl!RtlLengthSid` at `0x140006ef0`
- `ntoskrnl!RtlLengthSid` at `0x140006ed2`
- `ntoskrnl!RtlLengthSid` at `0x140006ef0`

## pseudocode

```c
__int64 __fastcall BfsGetNotPresentPolicyEntryLocked(__int64 a1, void *a2, void *a3, PRTL_DYNAMIC_HASH_TABLE_ENTRY *a4)
{
  ULONG v8; // eax
  ULONG v9; // eax
  ULONG_PTR v10; // rax
  struct _RTL_DYNAMIC_HASH_TABLE *v11; // rcx
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v12; // rax
  unsigned int v13; // ecx
  __int64 v15; // [rsp+50h] [rbp+8h] BYREF

  v15 = 0;
  v8 = RtlLengthSid(a2);
  BfsUpdateHash(a2, v8, &v15);
  v9 = RtlLengthSid(a3);
  BfsUpdateHash(a3, v9, &v15);
  v10 = BfsFinalHash(&v15);
  v11 = *(struct _RTL_DYNAMIC_HASH_TABLE **)(a1 + 8);
  *a4 = 0;
  v12 = BfsLookupPolicyEntryHashTable(v11, v10, a2, a3);
  if ( v12 )
  {
    _InterlockedIncrement((volatile signed __int32 *)&v12[6]);
    v13 = 0;
  }
  else
  {
    v13 = -1072103391;
  }
  *a4 = v12;
  return v13;
}

```

## disassembly

```asm
0x140006eb0  push    rbx
0x140006eb2  push    rsi
0x140006eb3  push    rdi
0x140006eb4  push    r14
0x140006eb6  sub     rsp, 28h
0x140006eba  mov     rsi, rcx
0x140006ebd  mov     [rsp+48h+arg_0], 0
0x140006ec6  mov     rcx, rdx; Sid
0x140006ec9  mov     r14, r9
0x140006ecc  mov     rbx, r8
0x140006ecf  mov     rdi, rdx
0x140006ed2  call    cs:__imp_RtlLengthSid
0x140006ed9  nop     dword ptr [rax+rax+00h]
0x140006ede  lea     r8, [rsp+48h+arg_0]
0x140006ee3  mov     rcx, rdi
0x140006ee6  mov     edx, eax
0x140006ee8  call    BfsUpdateHash
0x140006eed  mov     rcx, rbx; Sid
0x140006ef0  call    cs:__imp_RtlLengthSid
0x140006ef7  nop     dword ptr [rax+rax+00h]
0x140006efc  lea     r8, [rsp+48h+arg_0]
0x140006f01  mov     rcx, rbx
0x140006f04  mov     edx, eax
0x140006f06  call    BfsUpdateHash
0x140006f0b  lea     rcx, [rsp+48h+arg_0]
0x140006f10  call    BfsFinalHash
0x140006f15  mov     rcx, [rsi+8]; HashTable
0x140006f19  mov     rdx, rax
0x140006f1c  mov     r9, rbx
0x140006f1f  mov     qword ptr [r14], 0
0x140006f26  mov     r8, rdi
0x140006f29  call    BfsLookupPolicyEntryHashTable
0x140006f2e  test    rax, rax
0x140006f31  jz      short loc_140006F3E
0x140006f33  lock inc dword ptr [rax+90h]
0x140006f3a  xor     ecx, ecx
0x140006f3c  jmp     short loc_140006F43
0x140006f3e  mov     ecx, 0C0190021h
0x140006f43  mov     [r14], rax
0x140006f46  mov     eax, ecx
0x140006f48  add     rsp, 28h
0x140006f4c  pop     r14
0x140006f4e  pop     rdi
0x140006f4f  pop     rsi
0x140006f50  pop     rbx
0x140006f51  retn
```
