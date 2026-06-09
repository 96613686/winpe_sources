# BfsGetNotPresentPolicyEntry

- ea: `0x140006db4`
- end: `0x140006ea8`
- name: `BfsGetNotPresentPolicyEntry`
- size: `244`
- prototype: `__int64 __fastcall(__int64, void *, void *, __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140005768`

## callees

- `0x1400017b0`
- `0x140006db4`
- `0x140008e38`
- `0x140012d00`

## import_xrefs

- `ntoskrnl!RtlLengthSid` at `0x140006dde`
- `ntoskrnl!RtlLengthSid` at `0x140006dfc`
- `ntoskrnl!RtlLengthSid` at `0x140006dde`
- `ntoskrnl!RtlLengthSid` at `0x140006dfc`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140006e3c`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140006e3c`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140006e77`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140006e77`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140006e2b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140006e2b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140006e83`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140006e83`

## pseudocode

```c
__int64 __fastcall BfsGetNotPresentPolicyEntry(__int64 a1, void *a2, void *a3, __int64 *a4)
{
  ULONG v8; // eax
  ULONG v9; // eax
  __int64 v10; // rax
  __int64 v11; // rbx
  unsigned int v12; // edi
  __int64 result; // rax
  __int64 v14; // [rsp+40h] [rbp+8h] BYREF

  v14 = 0;
  v8 = RtlLengthSid(a2);
  BfsUpdateHash(a2, v8, &v14);
  v9 = RtlLengthSid(a3);
  BfsUpdateHash(a3, v9, &v14);
  BfsFinalHash(&v14);
  *a4 = 0;
  KeEnterCriticalRegion();
  ExAcquirePushLockSharedEx(a1, 0);
  v10 = BfsLookupPolicyEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 8));
  v11 = v10;
  if ( v10 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v10 + 144));
    v12 = 0;
  }
  else
  {
    v12 = -1072103391;
  }
  ExReleasePushLockSharedEx(a1, 0);
  KeLeaveCriticalRegion();
  result = v12;
  *a4 = v11;
  return result;
}

```

## disassembly

```asm
0x140006db4  mov     [rsp+arg_8], rbx
0x140006db9  mov     [rsp+arg_10], rbp
0x140006dbe  push    rsi
0x140006dbf  push    rdi
0x140006dc0  push    r14
0x140006dc2  sub     rsp, 20h
0x140006dc6  mov     rbp, rcx
0x140006dc9  mov     [rsp+38h+arg_0], 0
0x140006dd2  mov     rcx, rdx; Sid
0x140006dd5  mov     r14, r9
0x140006dd8  mov     rdi, r8
0x140006ddb  mov     rsi, rdx
0x140006dde  call    cs:__imp_RtlLengthSid
0x140006de5  nop     dword ptr [rax+rax+00h]
0x140006dea  lea     r8, [rsp+38h+arg_0]
0x140006def  mov     rcx, rsi
0x140006df2  mov     edx, eax
0x140006df4  call    BfsUpdateHash
0x140006df9  mov     rcx, rdi; Sid
0x140006dfc  call    cs:__imp_RtlLengthSid
0x140006e03  nop     dword ptr [rax+rax+00h]
0x140006e08  lea     r8, [rsp+38h+arg_0]
0x140006e0d  mov     rcx, rdi
0x140006e10  mov     edx, eax
0x140006e12  call    BfsUpdateHash
0x140006e17  lea     rcx, [rsp+38h+arg_0]
0x140006e1c  call    BfsFinalHash
0x140006e21  mov     rbx, rax
0x140006e24  mov     qword ptr [r14], 0
0x140006e2b  call    cs:__imp_KeEnterCriticalRegion
0x140006e32  nop     dword ptr [rax+rax+00h]
0x140006e37  xor     edx, edx
0x140006e39  mov     rcx, rbp
0x140006e3c  call    cs:__imp_ExAcquirePushLockSharedEx
0x140006e43  nop     dword ptr [rax+rax+00h]
0x140006e48  mov     rcx, [rbp+8]; HashTable
0x140006e4c  mov     r9, rdi
0x140006e4f  mov     r8, rsi
0x140006e52  mov     rdx, rbx
0x140006e55  call    BfsLookupPolicyEntryHashTable
0x140006e5a  mov     rbx, rax
0x140006e5d  test    rax, rax
0x140006e60  jz      short loc_140006E6D
0x140006e62  lock inc dword ptr [rax+90h]
0x140006e69  xor     edi, edi
0x140006e6b  jmp     short loc_140006E72
0x140006e6d  mov     edi, 0C0190021h
0x140006e72  xor     edx, edx
0x140006e74  mov     rcx, rbp
0x140006e77  call    cs:__imp_ExReleasePushLockSharedEx
0x140006e7e  nop     dword ptr [rax+rax+00h]
0x140006e83  call    cs:__imp_KeLeaveCriticalRegion
0x140006e8a  nop     dword ptr [rax+rax+00h]
0x140006e8f  mov     rbp, [rsp+38h+arg_10]
0x140006e94  mov     eax, edi
0x140006e96  mov     [r14], rbx
0x140006e99  mov     rbx, [rsp+38h+arg_8]
0x140006e9e  add     rsp, 20h
0x140006ea2  pop     r14
0x140006ea4  pop     rdi
0x140006ea5  pop     rsi
0x140006ea6  retn
```
