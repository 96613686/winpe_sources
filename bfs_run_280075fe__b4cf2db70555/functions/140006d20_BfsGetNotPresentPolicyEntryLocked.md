# BfsGetNotPresentPolicyEntryLocked

- ea: `0x140006d20`
- end: `0x140006dc3`
- name: `BfsGetNotPresentPolicyEntryLocked`
- size: `163`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14000ebf4`

## callees

- `0x140001bc0`
- `0x140006d20`
- `0x140008ca8`
- `0x140012bc8`

## import_xrefs

- `ntoskrnl!RtlLengthSid` at `0x140006d42`
- `ntoskrnl!RtlLengthSid` at `0x140006d60`
- `ntoskrnl!RtlLengthSid` at `0x140006d42`
- `ntoskrnl!RtlLengthSid` at `0x140006d60`

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
0x140006d20  push    rbx
0x140006d22  push    rsi
0x140006d23  push    rdi
0x140006d24  push    r14
0x140006d26  sub     rsp, 28h
0x140006d2a  mov     rsi, rcx
0x140006d2d  mov     [rsp+48h+arg_0], 0
0x140006d36  mov     rcx, rdx; Sid
0x140006d39  mov     r14, r9
0x140006d3c  mov     rbx, r8
0x140006d3f  mov     rdi, rdx
0x140006d42  call    cs:__imp_RtlLengthSid
0x140006d49  nop     dword ptr [rax+rax+00h]
0x140006d4e  lea     r8, [rsp+48h+arg_0]
0x140006d53  mov     rcx, rdi
0x140006d56  mov     edx, eax
0x140006d58  call    BfsUpdateHash
0x140006d5d  mov     rcx, rbx; Sid
0x140006d60  call    cs:__imp_RtlLengthSid
0x140006d67  nop     dword ptr [rax+rax+00h]
0x140006d6c  lea     r8, [rsp+48h+arg_0]
0x140006d71  mov     rcx, rbx
0x140006d74  mov     edx, eax
0x140006d76  call    BfsUpdateHash
0x140006d7b  lea     rcx, [rsp+48h+arg_0]
0x140006d80  call    BfsFinalHash
0x140006d85  mov     rcx, [rsi+8]; HashTable
0x140006d89  mov     rdx, rax
0x140006d8c  mov     r9, rbx
0x140006d8f  mov     qword ptr [r14], 0
0x140006d96  mov     r8, rdi
0x140006d99  call    BfsLookupPolicyEntryHashTable
0x140006d9e  test    rax, rax
0x140006da1  jz      short loc_140006DAE
0x140006da3  lock inc dword ptr [rax+90h]
0x140006daa  xor     ecx, ecx
0x140006dac  jmp     short loc_140006DB3
0x140006dae  mov     ecx, 0C0190021h
0x140006db3  mov     [r14], rax
0x140006db6  mov     eax, ecx
0x140006db8  add     rsp, 28h
0x140006dbc  pop     r14
0x140006dbe  pop     rdi
0x140006dbf  pop     rsi
0x140006dc0  pop     rbx
0x140006dc1  retn
```
