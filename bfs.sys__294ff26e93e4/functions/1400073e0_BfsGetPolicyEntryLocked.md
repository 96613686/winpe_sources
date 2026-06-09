# BfsGetPolicyEntryLocked

- ea: `0x1400073e0`
- end: `0x140007615`
- name: `BfsGetPolicyEntryLocked`
- size: `565`
- prototype: `__int64 __fastcall(struct _FLT_FILTER *, __int64, __int64, void *, PSID Sid, _DWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14000ed84`

## callees

- `0x140001008`
- `0x1400017b0`
- `0x1400061d0`
- `0x1400073e0`
- `0x140008728`
- `0x140008e38`
- `0x140012d00`
- `0x140013860`

## import_xrefs

- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400074d7`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400074d7`
- `ntoskrnl!KeWaitForSingleObject` at `0x140007503`
- `ntoskrnl!KeWaitForSingleObject` at `0x140007503`
- `ntoskrnl!RtlLengthSid` at `0x14000742b`
- `ntoskrnl!RtlLengthSid` at `0x140007448`
- `ntoskrnl!RtlLengthSid` at `0x14000742b`
- `ntoskrnl!RtlLengthSid` at `0x140007448`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400074c9`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000757a`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400074c9`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000757a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400074e3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140007586`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400074e3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140007586`

## pseudocode

```c
__int64 __fastcall BfsGetPolicyEntryLocked(
        struct _FLT_FILTER *a1,
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
  char v20; // dl
  __int64 result; // rax
  int Timeout; // [rsp+20h] [rbp-61h]
  __int64 v23; // [rsp+40h] [rbp-41h] BYREF
  struct _FLT_FILTER *v24; // [rsp+48h] [rbp-39h]
  struct _EVENT_DATA_DESCRIPTOR v25; // [rsp+50h] [rbp-31h] BYREF
  __int64 *v26; // [rsp+70h] [rbp-11h]
  __int64 v27; // [rsp+78h] [rbp-9h]

  v24 = a1;
  v23 = 0;
  v9 = RtlLengthSid(a4);
  BfsUpdateHash(a4, v9, &v23);
  v10 = RtlLengthSid(Sid);
  BfsUpdateHash(Sid, v10, &v23);
  v11 = BfsFinalHash(&v23);
  *a7 = 0;
  v12 = v11;
  v13 = BfsLookupPolicyEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a3 + 8));
  v23 = v13;
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
          LODWORD(v23) = -1073741823;
          v26 = &v23;
          v27 = 4;
          tlgWriteTransfer_EtwWriteTransfer(v17, (int)&byte_140016D91, v18, v19, Timeout, &v25);
        }
        if ( v15 )
        {
          if ( *a6 == 2 )
          {
            v20 = 1;
          }
          else
          {
            if ( *a6 == 1 )
            {
              ExReleasePushLockSharedEx(a3, 0);
              KeLeaveCriticalRegion();
              *a6 = 0;
            }
            v20 = 0;
          }
          BfsDereferencePolicyEntryEx((char *)v15, v20);
        }
        return v16;
      }
    }
LABEL_21:
    _InterlockedExchange64((volatile __int64 *)(v15 + 96), MEMORY[0xFFFFF78000000014]);
    *a7 = v15;
    return v16;
  }
  if ( *a6 == 1 )
    return 3221226029LL;
  result = BfsInsertPolicyEntryLocked(v24, v14, a3, v12, (unsigned __int8 *)a4, (unsigned __int8 *)Sid, a6, &v23);
  v16 = result;
  if ( (int)result >= 0 )
  {
    v15 = v23;
    goto LABEL_21;
  }
  return result;
}

```

## disassembly

```asm
0x1400073e0  mov     [rsp-8+arg_8], rbx
0x1400073e5  push    rbp
0x1400073e6  push    rsi
0x1400073e7  push    rdi
0x1400073e8  push    r12
0x1400073ea  push    r13
0x1400073ec  push    r14
0x1400073ee  push    r15
0x1400073f0  lea     rbp, [rsp-0Fh]
0x1400073f5  sub     rsp, 90h
0x1400073fc  mov     rax, cs:__security_cookie
0x140007403  xor     rax, rsp
0x140007406  mov     [rbp+3Fh+var_40], rax
0x14000740a  mov     r15, [rbp+3Fh+Sid]
0x14000740e  mov     rdi, r9
0x140007411  mov     rsi, [rbp+3Fh+arg_28]
0x140007415  mov     r14, r8
0x140007418  mov     r13, [rbp+3Fh+arg_30]
0x14000741c  mov     [rbp+3Fh+var_78], rcx
0x140007420  mov     rcx, r9; Sid
0x140007423  mov     [rbp+3Fh+var_80], 0
0x14000742b  call    cs:__imp_RtlLengthSid
0x140007432  nop     dword ptr [rax+rax+00h]
0x140007437  lea     r8, [rbp+3Fh+var_80]
0x14000743b  mov     rcx, rdi
0x14000743e  mov     edx, eax
0x140007440  call    BfsUpdateHash
0x140007445  mov     rcx, r15; Sid
0x140007448  call    cs:__imp_RtlLengthSid
0x14000744f  nop     dword ptr [rax+rax+00h]
0x140007454  lea     r8, [rbp+3Fh+var_80]
0x140007458  mov     rcx, r15
0x14000745b  mov     edx, eax
0x14000745d  call    BfsUpdateHash
0x140007462  lea     rcx, [rbp+3Fh+var_80]
0x140007466  call    BfsFinalHash
0x14000746b  mov     qword ptr [r13+0], 0
0x140007473  mov     rdx, rax
0x140007476  mov     rcx, [r14+8]; HashTable
0x14000747a  mov     r9, r15
0x14000747d  mov     r8, rdi
0x140007480  mov     r12, rax
0x140007483  call    BfsLookupPolicyEntryHashTable
0x140007488  mov     [rbp+3Fh+var_80], rax
0x14000748c  mov     rbx, rax
0x14000748f  test    rax, rax
0x140007492  jz      loc_140007599
0x140007498  test    dword ptr [rax+38h], 10000000h
0x14000749f  jz      loc_140007599
0x1400074a5  lock inc dword ptr [rax+90h]
0x1400074ac  xor     r15d, r15d
0x1400074af  cmp     dword ptr [rax+38h], 10000001h
0x1400074b6  mov     edi, r15d
0x1400074b9  jnz     loc_1400075D6
0x1400074bf  xor     edx, edx
0x1400074c1  mov     rcx, r14
0x1400074c4  cmp     dword ptr [rsi], 1
0x1400074c7  jnz     short loc_1400074D7
0x1400074c9  call    cs:__imp_ExReleasePushLockSharedEx
0x1400074d0  nop     dword ptr [rax+rax+00h]
0x1400074d5  jmp     short loc_1400074E3
0x1400074d7  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400074de  nop     dword ptr [rax+rax+00h]
0x1400074e3  call    cs:__imp_KeLeaveCriticalRegion
0x1400074ea  nop     dword ptr [rax+rax+00h]
0x1400074ef  mov     [rsi], r15d
0x1400074f2  xor     r9d, r9d; Alertable
0x1400074f5  mov     rcx, [rbx+28h]; Object
0x1400074f9  xor     r8d, r8d; WaitMode
0x1400074fc  xor     edx, edx; WaitReason
0x1400074fe  mov     [rsp+0C0h+Timeout], r15; int
0x140007503  call    cs:__imp_KeWaitForSingleObject
0x14000750a  nop     dword ptr [rax+rax+00h]
0x14000750f  cmp     dword ptr [rbx+38h], 10000000h
0x140007516  jz      loc_1400075D6
0x14000751c  mov     eax, cs:dword_140019000
0x140007522  mov     edi, 0C0000001h
0x140007527  cmp     eax, 3
0x14000752a  jbe     short loc_140007554
0x14000752c  lea     rax, [rbp+3Fh+var_80]
0x140007530  mov     dword ptr [rbp+3Fh+var_80], edi
0x140007533  mov     [rbp+3Fh+var_50], rax
0x140007537  lea     rdx, byte_140016D91; int
0x14000753e  lea     rax, [rbp+3Fh+var_70]
0x140007542  mov     [rbp+3Fh+var_48], 4
0x14000754a  mov     [rsp+0C0h+var_98], rax; PEVENT_DATA_DESCRIPTOR
0x14000754f  call    _tlgWriteTransfer_EtwWriteTransfer
0x140007554  test    rbx, rbx
0x140007557  jz      loc_1400075EB
0x14000755d  mov     eax, [rsi]
0x14000755f  cmp     eax, 2
0x140007562  jnz     short loc_140007570
0x140007564  mov     dl, 1
0x140007566  mov     rcx, rbx; P
0x140007569  call    BfsDereferencePolicyEntryEx
0x14000756e  jmp     short loc_1400075EB
0x140007570  cmp     eax, 1
0x140007573  jnz     short loc_140007595
0x140007575  xor     edx, edx
0x140007577  mov     rcx, r14
0x14000757a  call    cs:__imp_ExReleasePushLockSharedEx
0x140007581  nop     dword ptr [rax+rax+00h]
0x140007586  call    cs:__imp_KeLeaveCriticalRegion
0x14000758d  nop     dword ptr [rax+rax+00h]
0x140007592  mov     [rsi], r15d
0x140007595  xor     edx, edx
0x140007597  jmp     short loc_140007566
0x140007599  cmp     dword ptr [rsi], 1
0x14000759c  jnz     short loc_1400075A5
0x14000759e  mov     eax, 0C000022Dh
0x1400075a3  jmp     short loc_1400075ED
0x1400075a5  mov     rcx, [rbp+3Fh+var_78]
0x1400075a9  lea     rax, [rbp+3Fh+var_80]
0x1400075ad  mov     [rsp+0C0h+var_88], rax
0x1400075b2  mov     r9, r12
0x1400075b5  mov     [rsp+0C0h+var_90], rsi
0x1400075ba  mov     r8, r14
0x1400075bd  mov     [rsp+0C0h+var_98], r15
0x1400075c2  mov     [rsp+0C0h+Timeout], rdi
0x1400075c7  call    BfsInsertPolicyEntryLocked
0x1400075cc  mov     edi, eax
0x1400075ce  test    eax, eax
0x1400075d0  js      short loc_1400075ED
0x1400075d2  mov     rbx, [rbp+3Fh+var_80]
0x1400075d6  mov     rax, 0FFFFF78000000014h
0x1400075e0  mov     rax, [rax]
0x1400075e3  xchg    rax, [rbx+60h]
0x1400075e7  mov     [r13+0], rbx
0x1400075eb  mov     eax, edi
0x1400075ed  mov     rcx, [rbp+3Fh+var_40]
0x1400075f1  xor     rcx, rsp; StackCookie
0x1400075f4  call    __security_check_cookie
0x1400075f9  mov     rbx, [rsp+0C0h+arg_8]
0x140007601  add     rsp, 90h
0x140007608  pop     r15
0x14000760a  pop     r14
0x14000760c  pop     r13
0x14000760e  pop     r12
0x140007610  pop     rdi
0x140007611  pop     rsi
0x140007612  pop     rbp
0x140007613  retn
```
