# BfsGetPolicyEntry

- ea: `0x140007044`
- end: `0x14000724a`
- name: `BfsGetPolicyEntry`
- size: `518`
- prototype: ``
- caller_count: `7`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1400055d8`
- `0x140005d4c`
- `0x140009530`
- `0x14000995c`
- `0x140009b9c`
- `0x14000c658`
- `0x14000dadc`

## callees

- `0x140001008`
- `0x140001bc0`
- `0x140006040`
- `0x140007044`
- `0x140007e5c`
- `0x140008ca8`
- `0x140012bc8`
- `0x140013730`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140007165`
- `ntoskrnl!KeWaitForSingleObject` at `0x140007165`
- `ntoskrnl!RtlLengthSid` at `0x14000708b`
- `ntoskrnl!RtlLengthSid` at `0x1400070a8`
- `ntoskrnl!RtlLengthSid` at `0x14000708b`
- `ntoskrnl!RtlLengthSid` at `0x1400070a8`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400070e6`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400070e6`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000712f`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400071cc`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000712f`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400071cc`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400070d5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400070d5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000713b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400071d8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000713b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400071d8`

## pseudocode

```c
__int64 __fastcall BfsGetPolicyEntry(__int64 a1, __int64 a2, __int64 a3, void *a4, PSID Sid, __int64 *a6)
{
  ULONG v9; // eax
  ULONG v10; // eax
  __int64 v11; // r12
  __int64 v12; // rax
  __int64 v13; // rbx
  unsigned int v14; // edi
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  __int64 result; // rax
  int Timeout; // [rsp+20h] [rbp-69h]
  __int64 v20; // [rsp+40h] [rbp-49h] BYREF
  __int64 v21; // [rsp+48h] [rbp-41h]
  struct _EVENT_DATA_DESCRIPTOR v22; // [rsp+50h] [rbp-39h] BYREF
  __int64 *v23; // [rsp+70h] [rbp-19h]
  __int64 v24; // [rsp+78h] [rbp-11h]

  v21 = a2;
  v20 = 0;
  v9 = RtlLengthSid(a4);
  BfsUpdateHash(a4, v9, &v20);
  v10 = RtlLengthSid(Sid);
  BfsUpdateHash(Sid, v10, &v20);
  v11 = BfsFinalHash(&v20);
  *a6 = 0;
  KeEnterCriticalRegion();
  ExAcquirePushLockSharedEx(a3, 0);
  v12 = BfsLookupPolicyEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a3 + 8));
  v20 = v12;
  v13 = v12;
  if ( v12 && (*(_DWORD *)(v12 + 56) & 0x10000000) != 0 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v12 + 144));
    v14 = 0;
    ExReleasePushLockSharedEx(a3, 0);
    KeLeaveCriticalRegion();
    if ( *(_DWORD *)(v13 + 56) == 268435457 )
    {
      KeWaitForSingleObject(*(PVOID *)(v13 + 40), Executive, 0, 0, 0);
      if ( *(_DWORD *)(v13 + 56) != 0x10000000 )
      {
        v14 = -1073741823;
        if ( (unsigned int)dword_140019000 > 3 )
        {
          LODWORD(v20) = -1073741823;
          v23 = &v20;
          v24 = 4;
          tlgWriteTransfer_EtwWriteTransfer(v15, (int)&byte_140016D91, v16, v17, Timeout, &v22);
        }
        if ( v13 )
          BfsDereferencePolicyEntryEx((PVOID)v13);
        return v14;
      }
    }
  }
  else
  {
    ExReleasePushLockSharedEx(a3, 0);
    KeLeaveCriticalRegion();
    result = BfsInsertPolicyEntry(a1, v21, a3, v11, (unsigned __int8 *)a4, (unsigned __int8 *)Sid, &v20);
    v14 = result;
    if ( (int)result < 0 )
      return result;
    v13 = v20;
  }
  _InterlockedExchange64((volatile __int64 *)(v13 + 96), MEMORY[0xFFFFF78000000014]);
  *a6 = v13;
  return v14;
}

```

## disassembly

```asm
0x140007044  push    rbp
0x140007046  push    rbx
0x140007047  push    rsi
0x140007048  push    rdi
0x140007049  push    r12
0x14000704b  push    r13
0x14000704d  push    r14
0x14000704f  push    r15
0x140007051  lea     rbp, [rsp-0Fh]
0x140007056  sub     rsp, 98h
0x14000705d  mov     rax, cs:__security_cookie
0x140007064  xor     rax, rsp
0x140007067  mov     [rbp+47h+var_50], rax
0x14000706b  mov     r14, [rbp+47h+Sid]
0x14000706f  mov     r13, rcx
0x140007072  mov     r15, [rbp+47h+arg_28]
0x140007076  mov     rcx, r9; Sid
0x140007079  mov     rdi, r9
0x14000707c  mov     [rbp+47h+var_88], rdx
0x140007080  mov     rsi, r8
0x140007083  mov     [rbp+47h+var_90], 0
0x14000708b  call    cs:__imp_RtlLengthSid
0x140007092  nop     dword ptr [rax+rax+00h]
0x140007097  lea     r8, [rbp+47h+var_90]
0x14000709b  mov     rcx, rdi
0x14000709e  mov     edx, eax
0x1400070a0  call    BfsUpdateHash
0x1400070a5  mov     rcx, r14; Sid
0x1400070a8  call    cs:__imp_RtlLengthSid
0x1400070af  nop     dword ptr [rax+rax+00h]
0x1400070b4  lea     r8, [rbp+47h+var_90]
0x1400070b8  mov     rcx, r14
0x1400070bb  mov     edx, eax
0x1400070bd  call    BfsUpdateHash
0x1400070c2  lea     rcx, [rbp+47h+var_90]
0x1400070c6  call    BfsFinalHash
0x1400070cb  mov     r12, rax
0x1400070ce  mov     qword ptr [r15], 0
0x1400070d5  call    cs:__imp_KeEnterCriticalRegion
0x1400070dc  nop     dword ptr [rax+rax+00h]
0x1400070e1  xor     edx, edx
0x1400070e3  mov     rcx, rsi
0x1400070e6  call    cs:__imp_ExAcquirePushLockSharedEx
0x1400070ed  nop     dword ptr [rax+rax+00h]
0x1400070f2  mov     rcx, [rsi+8]; HashTable
0x1400070f6  mov     r9, r14
0x1400070f9  mov     r8, rdi
0x1400070fc  mov     rdx, r12
0x1400070ff  call    BfsLookupPolicyEntryHashTable
0x140007104  mov     [rbp+47h+var_90], rax
0x140007108  mov     rbx, rax
0x14000710b  test    rax, rax
0x14000710e  jz      loc_1400071C7
0x140007114  test    dword ptr [rax+38h], 10000000h
0x14000711b  jz      loc_1400071C7
0x140007121  lock inc dword ptr [rax+90h]
0x140007128  xor     edx, edx
0x14000712a  mov     rcx, rsi
0x14000712d  xor     edi, edi
0x14000712f  call    cs:__imp_ExReleasePushLockSharedEx
0x140007136  nop     dword ptr [rax+rax+00h]
0x14000713b  call    cs:__imp_KeLeaveCriticalRegion
0x140007142  nop     dword ptr [rax+rax+00h]
0x140007147  cmp     dword ptr [rbx+38h], 10000001h
0x14000714e  jnz     loc_140007213
0x140007154  mov     rcx, [rbx+28h]; Object
0x140007158  xor     r9d, r9d; Alertable
0x14000715b  xor     r8d, r8d; WaitMode
0x14000715e  mov     [rsp+0D0h+Timeout], rdi; int
0x140007163  xor     edx, edx; WaitReason
0x140007165  call    cs:__imp_KeWaitForSingleObject
0x14000716c  nop     dword ptr [rax+rax+00h]
0x140007171  cmp     dword ptr [rbx+38h], 10000000h
0x140007178  jz      loc_140007213
0x14000717e  mov     eax, cs:dword_140019000
0x140007184  mov     edi, 0C0000001h
0x140007189  cmp     eax, 3
0x14000718c  jbe     short loc_1400071B6
0x14000718e  lea     rax, [rbp+47h+var_90]
0x140007192  mov     dword ptr [rbp+47h+var_90], edi
0x140007195  mov     [rbp+47h+var_60], rax
0x140007199  lea     rdx, byte_140016D91; int
0x1400071a0  lea     rax, [rbp+47h+var_80]
0x1400071a4  mov     [rbp+47h+var_58], 4
0x1400071ac  mov     [rsp+0D0h+var_A8], rax; PEVENT_DATA_DESCRIPTOR
0x1400071b1  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400071b6  test    rbx, rbx
0x1400071b9  jz      short loc_140007227
0x1400071bb  xor     edx, edx
0x1400071bd  mov     rcx, rbx; P
0x1400071c0  call    BfsDereferencePolicyEntryEx
0x1400071c5  jmp     short loc_140007227
0x1400071c7  xor     edx, edx
0x1400071c9  mov     rcx, rsi
0x1400071cc  call    cs:__imp_ExReleasePushLockSharedEx
0x1400071d3  nop     dword ptr [rax+rax+00h]
0x1400071d8  call    cs:__imp_KeLeaveCriticalRegion
0x1400071df  nop     dword ptr [rax+rax+00h]
0x1400071e4  mov     rdx, [rbp+47h+var_88]
0x1400071e8  lea     rax, [rbp+47h+var_90]
0x1400071ec  mov     [rsp+0D0h+var_A0], rax
0x1400071f1  mov     r9, r12
0x1400071f4  mov     [rsp+0D0h+var_A8], r14
0x1400071f9  mov     r8, rsi
0x1400071fc  mov     rcx, r13
0x1400071ff  mov     [rsp+0D0h+Timeout], rdi
0x140007204  call    BfsInsertPolicyEntry
0x140007209  mov     edi, eax
0x14000720b  test    eax, eax
0x14000720d  js      short loc_140007229
0x14000720f  mov     rbx, [rbp+47h+var_90]
0x140007213  mov     rax, 0FFFFF78000000014h
0x14000721d  mov     rax, [rax]
0x140007220  xchg    rax, [rbx+60h]
0x140007224  mov     [r15], rbx
0x140007227  mov     eax, edi
0x140007229  mov     rcx, [rbp+47h+var_50]
0x14000722d  xor     rcx, rsp; StackCookie
0x140007230  call    __security_check_cookie
0x140007235  add     rsp, 98h
0x14000723c  pop     r15
0x14000723e  pop     r14
0x140007240  pop     r13
0x140007242  pop     r12
0x140007244  pop     rdi
0x140007245  pop     rsi
0x140007246  pop     rbx
0x140007247  pop     rbp
0x140007248  retn
```
