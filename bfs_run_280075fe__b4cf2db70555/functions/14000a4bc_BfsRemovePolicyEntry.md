# BfsRemovePolicyEntry

- ea: `0x14000a4bc`
- end: `0x14000a797`
- name: `BfsRemovePolicyEntry`
- size: `731`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140009390`

## callees

- `0x140001008`
- `0x140001bc0`
- `0x140006040`
- `0x140008ca8`
- `0x140008d3c`
- `0x14000a4bc`
- `0x14000d3f8`
- `0x140012bc8`
- `0x140013730`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000a573`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000a573`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000a713`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000a713`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14000a5f0`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14000a62c`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14000a5f0`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14000a62c`
- `ntoskrnl!RtlLengthSid` at `0x14000a51c`
- `ntoskrnl!RtlLengthSid` at `0x14000a53a`
- `ntoskrnl!RtlLengthSid` at `0x14000a51c`
- `ntoskrnl!RtlLengthSid` at `0x14000a53a`
- `ntoskrnl!ZwDeleteFile` at `0x14000a6c7`
- `ntoskrnl!ZwDeleteFile` at `0x14000a6c7`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a5c8`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a5da`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a5c8`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a5da`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000a736`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000a74d`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000a736`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000a74d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000a562`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000a562`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000a71f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000a71f`
- `FLTMGR!FltClose` at `0x14000a761`
- `FLTMGR!FltClose` at `0x14000a761`

## pseudocode

```c
__int64 __fastcall BfsRemovePolicyEntry(int a1, __int64 a2, __int64 a3, void *a4, PSID Sid)
{
  HANDLE v6; // rdi
  ULONG v9; // eax
  ULONG v10; // eax
  __int64 v11; // rax
  void *v12; // rbx
  NTSTATUS v13; // eax
  int v14; // r8d
  int v15; // r9d
  NTSTATUS v16; // ebx
  int v17; // ecx
  int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  int v22; // [rsp+20h] [rbp-91h]
  __int64 v23; // [rsp+30h] [rbp-81h] BYREF
  int v24[2]; // [rsp+38h] [rbp-79h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+40h] [rbp-71h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-61h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-51h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v28; // [rsp+90h] [rbp-21h] BYREF
  __int64 *v29; // [rsp+B0h] [rbp-1h]
  __int64 v30; // [rsp+B8h] [rbp+7h]

  *(_QWORD *)v24 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v6 = 0;
  v23 = 0;
  UnicodeString = 0;
  DestinationString = 0;
  v9 = RtlLengthSid(a4);
  BfsUpdateHash(a4, v9, &v23);
  v10 = RtlLengthSid(Sid);
  BfsUpdateHash(Sid, v10, &v23);
  BfsFinalHash(&v23);
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(a3, 0);
  v11 = BfsLookupPolicyEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a3 + 8));
  v12 = (void *)v11;
  if ( v11 )
  {
    if ( *(_DWORD *)(v11 + 56) != 0x10000000 )
    {
      v16 = 0;
      goto LABEL_17;
    }
    *(_DWORD *)(v11 + 56) = 268435458;
    BfsRemoveAllPoliciesFromGlobalFileTable(&gBfsGlobalFileTable, v11);
    BfsDereferencePolicyEntryEx(v12);
  }
  RtlInitUnicodeString(&DestinationString, 0);
  RtlInitUnicodeString(&UnicodeString, 0);
  v13 = RtlConvertSidToUnicodeString(&DestinationString, a4, 1u);
  v16 = v13;
  if ( v13 < 0 )
  {
    v17 = dword_140019000;
    if ( (unsigned int)dword_140019000 <= 3 )
      goto LABEL_17;
    LODWORD(v23) = v13;
LABEL_16:
    v30 = 4;
    v29 = &v23;
    tlgWriteTransfer_EtwWriteTransfer(v17, (int)&byte_140016D91, v14, v15, v22, &v28);
    goto LABEL_17;
  }
  v16 = RtlConvertSidToUnicodeString(&UnicodeString, Sid, 1u);
  if ( v16 < 0 )
  {
LABEL_14:
    if ( (unsigned int)dword_140019000 <= 3 )
      goto LABEL_17;
    LODWORD(v23) = v16;
    goto LABEL_16;
  }
  LOBYTE(v15) = 1;
  v16 = BfsOpenPolicyDirectory(a1, 0, (unsigned int)&DestinationString, v15, (__int64)v24);
  if ( v16 >= 0 )
  {
    v6 = *(HANDLE *)v24;
    ObjectAttributes.RootDirectory = *(HANDLE *)v24;
    ObjectAttributes.ObjectName = &UnicodeString;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    ObjectAttributes.Length = 48;
    ObjectAttributes.Attributes = 64;
    v16 = ZwDeleteFile(&ObjectAttributes);
    if ( v16 >= 0 )
      goto LABEL_17;
    goto LABEL_14;
  }
  if ( (unsigned int)dword_140019000 > 3 )
  {
    LODWORD(v23) = v16;
    v29 = &v23;
    v30 = 4;
    tlgWriteTransfer_EtwWriteTransfer(v18, (int)&byte_140016D91, v19, v20, v22, &v28);
  }
  v6 = *(HANDLE *)v24;
LABEL_17:
  ExReleasePushLockExclusiveEx(a3, 0);
  KeLeaveCriticalRegion();
  if ( UnicodeString.Length )
    RtlFreeUnicodeString(&UnicodeString);
  if ( DestinationString.Length )
    RtlFreeUnicodeString(&DestinationString);
  if ( v6 )
    FltClose(v6);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x14000a4bc  mov     [rsp-8+arg_8], rbx
0x14000a4c1  push    rbp
0x14000a4c2  push    rsi
0x14000a4c3  push    rdi
0x14000a4c4  push    r12
0x14000a4c6  push    r13
0x14000a4c8  push    r14
0x14000a4ca  push    r15
0x14000a4cc  lea     rbp, [rsp-1Fh]
0x14000a4d1  sub     rsp, 0D0h
0x14000a4d8  mov     rax, cs:__security_cookie
0x14000a4df  xor     rax, rsp
0x14000a4e2  mov     [rbp+4Fh+var_40], rax
0x14000a4e6  mov     rsi, [rbp+4Fh+Sid]
0x14000a4ea  xorps   xmm0, xmm0
0x14000a4ed  xor     r13d, r13d
0x14000a4f0  mov     r12, rcx
0x14000a4f3  mov     rcx, r9; Sid
0x14000a4f6  mov     qword ptr [rbp+4Fh+var_C8], r13
0x14000a4fa  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm0
0x14000a4fe  mov     edi, r13d
0x14000a501  mov     [rsp+100h+var_D0], r13
0x14000a506  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm0
0x14000a50a  mov     r14, r9
0x14000a50d  mov     r15, r8
0x14000a510  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x14000a514  movups  xmmword ptr [rbp+4Fh+UnicodeString.Length], xmm0
0x14000a518  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x14000a51c  call    cs:__imp_RtlLengthSid
0x14000a523  nop     dword ptr [rax+rax+00h]
0x14000a528  lea     r8, [rsp+100h+var_D0]
0x14000a52d  mov     rcx, r14
0x14000a530  mov     edx, eax
0x14000a532  call    BfsUpdateHash
0x14000a537  mov     rcx, rsi; Sid
0x14000a53a  call    cs:__imp_RtlLengthSid
0x14000a541  nop     dword ptr [rax+rax+00h]
0x14000a546  lea     r8, [rsp+100h+var_D0]
0x14000a54b  mov     rcx, rsi
0x14000a54e  mov     edx, eax
0x14000a550  call    BfsUpdateHash
0x14000a555  lea     rcx, [rsp+100h+var_D0]
0x14000a55a  call    BfsFinalHash
0x14000a55f  mov     rbx, rax
0x14000a562  call    cs:__imp_KeEnterCriticalRegion
0x14000a569  nop     dword ptr [rax+rax+00h]
0x14000a56e  xor     edx, edx
0x14000a570  mov     rcx, r15
0x14000a573  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000a57a  nop     dword ptr [rax+rax+00h]
0x14000a57f  mov     rcx, [r15+8]; HashTable
0x14000a583  mov     r9, rsi
0x14000a586  mov     r8, r14
0x14000a589  mov     rdx, rbx
0x14000a58c  call    BfsLookupPolicyEntryHashTable
0x14000a591  mov     rbx, rax
0x14000a594  test    rax, rax
0x14000a597  jz      short loc_14000A5C2
0x14000a599  cmp     dword ptr [rax+38h], 10000000h
0x14000a5a0  jnz     short loc_14000A61A
0x14000a5a2  mov     rdx, rax
0x14000a5a5  mov     dword ptr [rax+38h], 10000002h
0x14000a5ac  lea     rcx, gBfsGlobalFileTable
0x14000a5b3  call    BfsRemoveAllPoliciesFromGlobalFileTable
0x14000a5b8  mov     dl, 1
0x14000a5ba  mov     rcx, rbx; P
0x14000a5bd  call    BfsDereferencePolicyEntryEx
0x14000a5c2  xor     edx, edx; SourceString
0x14000a5c4  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x14000a5c8  call    cs:__imp_RtlInitUnicodeString
0x14000a5cf  nop     dword ptr [rax+rax+00h]
0x14000a5d4  xor     edx, edx; SourceString
0x14000a5d6  lea     rcx, [rbp+4Fh+UnicodeString]; DestinationString
0x14000a5da  call    cs:__imp_RtlInitUnicodeString
0x14000a5e1  nop     dword ptr [rax+rax+00h]
0x14000a5e6  mov     r8b, 1; AllocateDestinationString
0x14000a5e9  lea     rcx, [rbp+4Fh+DestinationString]; UnicodeString
0x14000a5ed  mov     rdx, r14; Sid
0x14000a5f0  call    cs:__imp_RtlConvertSidToUnicodeString
0x14000a5f7  nop     dword ptr [rax+rax+00h]
0x14000a5fc  mov     ebx, eax
0x14000a5fe  test    eax, eax
0x14000a600  jns     short loc_14000A622
0x14000a602  mov     ecx, cs:dword_140019000
0x14000a608  cmp     ecx, 3
0x14000a60b  jbe     loc_14000A70E
0x14000a611  mov     dword ptr [rsp+100h+var_D0], eax
0x14000a615  jmp     loc_14000A6E8
0x14000a61a  mov     ebx, r13d
0x14000a61d  jmp     loc_14000A70E
0x14000a622  mov     r8b, 1; AllocateDestinationString
0x14000a625  lea     rcx, [rbp+4Fh+UnicodeString]; UnicodeString
0x14000a629  mov     rdx, rsi; Sid
0x14000a62c  call    cs:__imp_RtlConvertSidToUnicodeString
0x14000a633  nop     dword ptr [rax+rax+00h]
0x14000a638  mov     ebx, eax
0x14000a63a  test    eax, eax
0x14000a63c  js      loc_14000A6D9
0x14000a642  lea     rax, [rbp+4Fh+var_C8]
0x14000a646  mov     r9b, 1
0x14000a649  lea     r8, [rbp+4Fh+DestinationString]
0x14000a64d  mov     qword ptr [rsp+100h+var_E0], rax; int
0x14000a652  xor     edx, edx
0x14000a654  mov     rcx, r12
0x14000a657  call    BfsOpenPolicyDirectory
0x14000a65c  mov     ebx, eax
0x14000a65e  test    eax, eax
0x14000a660  jns     short loc_14000A69D
0x14000a662  mov     eax, cs:dword_140019000
0x14000a668  cmp     eax, 3
0x14000a66b  jbe     short loc_14000A697
0x14000a66d  lea     rax, [rsp+100h+var_D0]
0x14000a672  mov     dword ptr [rsp+100h+var_D0], ebx
0x14000a676  mov     [rbp+4Fh+var_50], rax
0x14000a67a  lea     rdx, byte_140016D91; int
0x14000a681  lea     rax, [rbp+4Fh+var_70]
0x14000a685  mov     [rbp+4Fh+var_48], 4
0x14000a68d  mov     [rsp+100h+var_D8], rax; PEVENT_DATA_DESCRIPTOR
0x14000a692  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000a697  mov     rdi, qword ptr [rbp+4Fh+var_C8]
0x14000a69b  jmp     short loc_14000A70E
0x14000a69d  mov     rdi, qword ptr [rbp+4Fh+var_C8]
0x14000a6a1  lea     rax, [rbp+4Fh+UnicodeString]
0x14000a6a5  xorps   xmm0, xmm0
0x14000a6a8  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], rdi
0x14000a6ac  lea     rcx, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x14000a6b0  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x14000a6b4  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x14000a6b9  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x14000a6c0  mov     [rbp+4Fh+ObjectAttributes.Attributes], 40h ; '@'
0x14000a6c7  call    cs:__imp_ZwDeleteFile
0x14000a6ce  nop     dword ptr [rax+rax+00h]
0x14000a6d3  mov     ebx, eax
0x14000a6d5  test    eax, eax
0x14000a6d7  jns     short loc_14000A70E
0x14000a6d9  mov     eax, cs:dword_140019000
0x14000a6df  cmp     eax, 3
0x14000a6e2  jbe     short loc_14000A70E
0x14000a6e4  mov     dword ptr [rsp+100h+var_D0], ebx
0x14000a6e8  lea     rax, [rsp+100h+var_D0]
0x14000a6ed  mov     [rbp+4Fh+var_48], 4
0x14000a6f5  mov     [rbp+4Fh+var_50], rax
0x14000a6f9  lea     rdx, byte_140016D91; int
0x14000a700  lea     rax, [rbp+4Fh+var_70]
0x14000a704  mov     [rsp+100h+var_D8], rax; PEVENT_DATA_DESCRIPTOR
0x14000a709  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000a70e  xor     edx, edx
0x14000a710  mov     rcx, r15
0x14000a713  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000a71a  nop     dword ptr [rax+rax+00h]
0x14000a71f  call    cs:__imp_KeLeaveCriticalRegion
0x14000a726  nop     dword ptr [rax+rax+00h]
0x14000a72b  cmp     [rbp+4Fh+UnicodeString.Length], r13w
0x14000a730  jbe     short loc_14000A742
0x14000a732  lea     rcx, [rbp+4Fh+UnicodeString]; UnicodeString
0x14000a736  call    cs:__imp_RtlFreeUnicodeString
0x14000a73d  nop     dword ptr [rax+rax+00h]
0x14000a742  cmp     [rbp+4Fh+DestinationString.Length], r13w
0x14000a747  jbe     short loc_14000A759
0x14000a749  lea     rcx, [rbp+4Fh+DestinationString]; UnicodeString
0x14000a74d  call    cs:__imp_RtlFreeUnicodeString
0x14000a754  nop     dword ptr [rax+rax+00h]
0x14000a759  test    rdi, rdi
0x14000a75c  jz      short loc_14000A76D
0x14000a75e  mov     rcx, rdi; FileHandle
0x14000a761  call    cs:__imp_FltClose
0x14000a768  nop     dword ptr [rax+rax+00h]
0x14000a76d  mov     eax, ebx
0x14000a76f  mov     rcx, [rbp+4Fh+var_40]
0x14000a773  xor     rcx, rsp; StackCookie
0x14000a776  call    __security_check_cookie
0x14000a77b  mov     rbx, [rsp+100h+arg_8]
0x14000a783  add     rsp, 0D0h
0x14000a78a  pop     r15
0x14000a78c  pop     r14
0x14000a78e  pop     r13
0x14000a790  pop     r12
0x14000a792  pop     rdi
0x14000a793  pop     rsi
0x14000a794  pop     rbp
0x14000a795  retn
```
