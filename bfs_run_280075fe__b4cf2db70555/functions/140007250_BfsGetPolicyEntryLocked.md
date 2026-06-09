# BfsGetPolicyEntryLocked

- ea: `0x140007250`
- end: `0x140007485`
- name: `BfsGetPolicyEntryLocked`
- size: `565`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14000ebf4`

## callees

- `0x140001008`
- `0x140001bc0`
- `0x140006040`
- `0x140007250`
- `0x140008598`
- `0x140008ca8`
- `0x140012bc8`
- `0x140013730`

## import_xrefs

- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140007347`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140007347`
- `ntoskrnl!KeWaitForSingleObject` at `0x140007373`
- `ntoskrnl!KeWaitForSingleObject` at `0x140007373`
- `ntoskrnl!RtlLengthSid` at `0x14000729b`
- `ntoskrnl!RtlLengthSid` at `0x1400072b8`
- `ntoskrnl!RtlLengthSid` at `0x14000729b`
- `ntoskrnl!RtlLengthSid` at `0x1400072b8`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140007339`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400073ea`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140007339`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400073ea`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140007353`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400073f6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140007353`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400073f6`

## pseudocode

```c
__int64 __fastcall BfsGetPolicyEntryLocked(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        void *a4,
        PSID Sid,
        _DWORD *a6,
        __int64 *a7)
{
  ULONG v9; // eax
  ULONG v10; // eax
  __int64 v11; // rax
  __int64 v12; // r12
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rbx
  unsigned int v16; // edi
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  __int64 result; // rax
  int Timeout; // [rsp+20h] [rbp-61h]
  __int64 v22; // [rsp+40h] [rbp-41h] BYREF
  __int64 v23; // [rsp+48h] [rbp-39h]
  struct _EVENT_DATA_DESCRIPTOR v24; // [rsp+50h] [rbp-31h] BYREF
  __int64 *v25; // [rsp+70h] [rbp-11h]
  __int64 v26; // [rsp+78h] [rbp-9h]

  v23 = a1;
  v22 = 0;
  v9 = RtlLengthSid(a4);
  BfsUpdateHash(a4, v9, &v22);
  v10 = RtlLengthSid(Sid);
  BfsUpdateHash(Sid, v10, &v22);
  v11 = BfsFinalHash(&v22);
  *a7 = 0;
  v12 = v11;
  v13 = BfsLookupPolicyEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a3 + 8));
  v22 = v13;
  v15 = v13;
  if ( v13 && (*(_DWORD *)(v13 + 56) & 0x10000000) != 0 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v13 + 144));
    v16 = 0;
    if ( *(_DWORD *)(v13 + 56) == 268435457 )
    {
      if ( *a6 == 1 )
        ExReleasePushLockSharedEx(a3, 0);
      else
        ExReleasePushLockExclusiveEx(a3, 0);
      KeLeaveCriticalRegion();
      *a6 = 0;
      KeWaitForSingleObject(*(PVOID *)(v15 + 40), Executive, 0, 0, 0);
      if ( *(_DWORD *)(v15 + 56) != 0x10000000 )
      {
        v16 = -1073741823;
        if ( (unsigned int)dword_140019000 > 3 )
        {
          LODWORD(v22) = -1073741823;
          v25 = &v22;
          v26 = 4;
          tlgWriteTransfer_EtwWriteTransfer(v17, (int)&byte_140016D91, v18, v19, Timeout, &v24);
        }
        if ( v15 )
        {
          if ( *a6 == 1 )
          {
            ExReleasePushLockSharedEx(a3, 0);
            KeLeaveCriticalRegion();
            *a6 = 0;
          }
          BfsDereferencePolicyEntryEx((PVOID)v15);
        }
        return v16;
      }
    }
LABEL_18:
    _InterlockedExchange64((volatile __int64 *)(v15 + 96), MEMORY[0xFFFFF78000000014]);
    *a7 = v15;
    return v16;
  }
  if ( *a6 == 1 )
    return 3221226029LL;
  result = BfsInsertPolicyEntryLocked(v23, v14, a3, v12, (unsigned __int8 *)a4, (unsigned __int8 *)Sid, a6, &v22);
  v16 = result;
  if ( (int)result >= 0 )
  {
    v15 = v22;
    goto LABEL_18;
  }
  return result;
}

```

## disassembly

```asm
0x140007250  mov     [rsp-8+arg_8], rbx
0x140007255  push    rbp
0x140007256  push    rsi
0x140007257  push    rdi
0x140007258  push    r12
0x14000725a  push    r13
0x14000725c  push    r14
0x14000725e  push    r15
0x140007260  lea     rbp, [rsp-0Fh]
0x140007265  sub     rsp, 90h
0x14000726c  mov     rax, cs:__security_cookie
0x140007273  xor     rax, rsp
0x140007276  mov     [rbp+3Fh+var_40], rax
0x14000727a  mov     r15, [rbp+3Fh+Sid]
0x14000727e  mov     rdi, r9
0x140007281  mov     rsi, [rbp+3Fh+arg_28]
0x140007285  mov     r14, r8
0x140007288  mov     r13, [rbp+3Fh+arg_30]
0x14000728c  mov     [rbp+3Fh+var_78], rcx
0x140007290  mov     rcx, r9; Sid
0x140007293  mov     [rbp+3Fh+var_80], 0
0x14000729b  call    cs:__imp_RtlLengthSid
0x1400072a2  nop     dword ptr [rax+rax+00h]
0x1400072a7  lea     r8, [rbp+3Fh+var_80]
0x1400072ab  mov     rcx, rdi
0x1400072ae  mov     edx, eax
0x1400072b0  call    BfsUpdateHash
0x1400072b5  mov     rcx, r15; Sid
0x1400072b8  call    cs:__imp_RtlLengthSid
0x1400072bf  nop     dword ptr [rax+rax+00h]
0x1400072c4  lea     r8, [rbp+3Fh+var_80]
0x1400072c8  mov     rcx, r15
0x1400072cb  mov     edx, eax
0x1400072cd  call    BfsUpdateHash
0x1400072d2  lea     rcx, [rbp+3Fh+var_80]
0x1400072d6  call    BfsFinalHash
0x1400072db  mov     qword ptr [r13+0], 0
0x1400072e3  mov     rdx, rax
0x1400072e6  mov     rcx, [r14+8]; HashTable
0x1400072ea  mov     r9, r15
0x1400072ed  mov     r8, rdi
0x1400072f0  mov     r12, rax
0x1400072f3  call    BfsLookupPolicyEntryHashTable
0x1400072f8  mov     [rbp+3Fh+var_80], rax
0x1400072fc  mov     rbx, rax
0x1400072ff  test    rax, rax
0x140007302  jz      loc_140007409
0x140007308  test    dword ptr [rax+38h], 10000000h
0x14000730f  jz      loc_140007409
0x140007315  lock inc dword ptr [rax+90h]
0x14000731c  xor     r15d, r15d
0x14000731f  cmp     dword ptr [rax+38h], 10000001h
0x140007326  mov     edi, r15d
0x140007329  jnz     loc_140007446
0x14000732f  xor     edx, edx
0x140007331  mov     rcx, r14
0x140007334  cmp     dword ptr [rsi], 1
0x140007337  jnz     short loc_140007347
0x140007339  call    cs:__imp_ExReleasePushLockSharedEx
0x140007340  nop     dword ptr [rax+rax+00h]
0x140007345  jmp     short loc_140007353
0x140007347  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000734e  nop     dword ptr [rax+rax+00h]
0x140007353  call    cs:__imp_KeLeaveCriticalRegion
0x14000735a  nop     dword ptr [rax+rax+00h]
0x14000735f  mov     [rsi], r15d
0x140007362  xor     r9d, r9d; Alertable
0x140007365  mov     rcx, [rbx+28h]; Object
0x140007369  xor     r8d, r8d; WaitMode
0x14000736c  xor     edx, edx; WaitReason
0x14000736e  mov     [rsp+0C0h+Timeout], r15; int
0x140007373  call    cs:__imp_KeWaitForSingleObject
0x14000737a  nop     dword ptr [rax+rax+00h]
0x14000737f  cmp     dword ptr [rbx+38h], 10000000h
0x140007386  jz      loc_140007446
0x14000738c  mov     eax, cs:dword_140019000
0x140007392  mov     edi, 0C0000001h
0x140007397  cmp     eax, 3
0x14000739a  jbe     short loc_1400073C4
0x14000739c  lea     rax, [rbp+3Fh+var_80]
0x1400073a0  mov     dword ptr [rbp+3Fh+var_80], edi
0x1400073a3  mov     [rbp+3Fh+var_50], rax
0x1400073a7  lea     rdx, byte_140016D91; int
0x1400073ae  lea     rax, [rbp+3Fh+var_70]
0x1400073b2  mov     [rbp+3Fh+var_48], 4
0x1400073ba  mov     [rsp+0C0h+var_98], rax; PEVENT_DATA_DESCRIPTOR
0x1400073bf  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400073c4  test    rbx, rbx
0x1400073c7  jz      loc_14000745B
0x1400073cd  mov     eax, [rsi]
0x1400073cf  cmp     eax, 2
0x1400073d2  jnz     short loc_1400073E0
0x1400073d4  mov     dl, 1
0x1400073d6  mov     rcx, rbx; P
0x1400073d9  call    BfsDereferencePolicyEntryEx
0x1400073de  jmp     short loc_14000745B
0x1400073e0  cmp     eax, 1
0x1400073e3  jnz     short loc_140007405
0x1400073e5  xor     edx, edx
0x1400073e7  mov     rcx, r14
0x1400073ea  call    cs:__imp_ExReleasePushLockSharedEx
0x1400073f1  nop     dword ptr [rax+rax+00h]
0x1400073f6  call    cs:__imp_KeLeaveCriticalRegion
0x1400073fd  nop     dword ptr [rax+rax+00h]
0x140007402  mov     [rsi], r15d
0x140007405  xor     edx, edx
0x140007407  jmp     short loc_1400073D6
0x140007409  cmp     dword ptr [rsi], 1
0x14000740c  jnz     short loc_140007415
0x14000740e  mov     eax, 0C000022Dh
0x140007413  jmp     short loc_14000745D
0x140007415  mov     rcx, [rbp+3Fh+var_78]
0x140007419  lea     rax, [rbp+3Fh+var_80]
0x14000741d  mov     [rsp+0C0h+var_88], rax
0x140007422  mov     r9, r12
0x140007425  mov     [rsp+0C0h+var_90], rsi
0x14000742a  mov     r8, r14
0x14000742d  mov     [rsp+0C0h+var_98], r15
0x140007432  mov     [rsp+0C0h+Timeout], rdi
0x140007437  call    BfsInsertPolicyEntryLocked
0x14000743c  mov     edi, eax
0x14000743e  test    eax, eax
0x140007440  js      short loc_14000745D
0x140007442  mov     rbx, [rbp+3Fh+var_80]
0x140007446  mov     rax, 0FFFFF78000000014h
0x140007450  mov     rax, [rax]
0x140007453  xchg    rax, [rbx+60h]
0x140007457  mov     [r13+0], rbx
0x14000745b  mov     eax, edi
0x14000745d  mov     rcx, [rbp+3Fh+var_40]
0x140007461  xor     rcx, rsp; StackCookie
0x140007464  call    __security_check_cookie
0x140007469  mov     rbx, [rsp+0C0h+arg_8]
0x140007471  add     rsp, 90h
0x140007478  pop     r15
0x14000747a  pop     r14
0x14000747c  pop     r13
0x14000747e  pop     r12
0x140007480  pop     rdi
0x140007481  pop     rsi
0x140007482  pop     rbp
0x140007483  retn
```
