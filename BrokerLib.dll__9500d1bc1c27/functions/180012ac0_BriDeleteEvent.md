# _BriDeleteEvent

- ea: `0x180012ac0`
- end: `0x180012cc1`
- name: `_BriDeleteEvent`
- size: `513`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x18000ae30`
- `0x18000af58`
- `0x18000aff4`
- `0x180012ac0`
- `0x180015af0`

## import_xrefs

- `ntdll!RtlRbRemoveNode` at `0x180012b4a`
- `ntdll!RtlRbRemoveNode` at `0x180012b4a`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180012b1d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180012b1d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180012b57`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180012b8a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180012b57`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180012b8a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180012c9e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180012c9e`

## pseudocode

```c
__int64 __fastcall BriDeleteEvent(__int64 a1, unsigned int a2, unsigned __int64 *a3)
{
  __int64 v5; // r14
  unsigned int v6; // ebx
  unsigned __int64 v7; // rbx
  struct _BR_RPC_CONTEXT_ENTRY *v8; // rax
  struct _BR_RPC_CONTEXT_ENTRY *v9; // rbx
  __int128 *v10; // rax
  char v12; // [rsp+30h] [rbp-79h] BYREF
  _DWORD v13[3]; // [rsp+34h] [rbp-75h] BYREF
  __int64 v14; // [rsp+40h] [rbp-69h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-61h] BYREF
  __int128 v16; // [rsp+58h] [rbp-51h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+70h] [rbp-39h] BYREF
  void *v18; // [rsp+80h] [rbp-29h]
  int v19; // [rsp+88h] [rbp-21h]
  int v20; // [rsp+8Ch] [rbp-1Dh]
  __int64 *v21; // [rsp+90h] [rbp-19h]
  __int64 v22; // [rsp+98h] [rbp-11h]
  __int128 *v23; // [rsp+A0h] [rbp-9h]
  __int64 v24; // [rsp+A8h] [rbp-1h]
  _DWORD *v25; // [rsp+B0h] [rbp+7h]
  __int64 v26; // [rsp+B8h] [rbp+Fh]
  char *v27; // [rsp+C0h] [rbp+17h]
  __int64 v28; // [rsp+C8h] [rbp+1Fh]

  v5 = -1;
  v16 = BLP_TRACELOGGING_INVALID_GUID;
  if ( a3 )
  {
    v7 = *a3;
    RtlAcquireSRWLockExclusive(&RpcContextTable);
    v8 = BrpRpcContextFindWithLockHeld(v7);
    v9 = v8;
    if ( !v8 || BrpRpcClientProcessHandleCheck(*((HANDLE *)v8 + 4)) )
    {
      RtlReleaseSRWLockExclusive(&RpcContextTable);
      v6 = 6;
    }
    else
    {
      RtlRbRemoveNode(&xmmword_180028970, v9);
      RtlReleaseSRWLockExclusive(&RpcContextTable);
      v10 = (__int128 *)*((_QWORD *)v9 + 9);
      v5 = *((_QWORD *)v9 + 10);
      if ( v10 )
        v16 = *v10;
      BrpRpcContextEntryDestroy(v9, a2);
      *a3 = 0;
      v6 = 0;
    }
  }
  else
  {
    v6 = 87;
  }
  if ( (unsigned int)dword_180028000 > 4 && (qword_180028010 & 1) != 0 && (qword_180028018 & 1) == qword_180028018 )
  {
    v12 = a2;
    v27 = &v12;
    v13[0] = v6;
    v25 = v13;
    v14 = v5;
    v23 = &v16;
    v28 = 1;
    v21 = &v14;
    *(_DWORD *)&EventDescriptor.Level = 4;
    UserData.Ptr = (ULONGLONG)off_180028008;
    v26 = 4;
    v24 = 16;
    v22 = 8;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 1;
    UserData.Size = *(unsigned __int16 *)off_180028008;
    v18 = &unk_180022405;
    UserData.Reserved = 2;
    v19 = 59;
    v20 = 1;
    v13[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 6u, &UserData);
  }
  return v6;
}

```

## disassembly

```asm
0x180012ac0  push    rbp
0x180012ac2  push    rbx
0x180012ac3  push    rsi
0x180012ac4  push    r14
0x180012ac6  push    r15
0x180012ac8  lea     rbp, [rsp-37h]
0x180012acd  sub     rsp, 0E0h
0x180012ad4  mov     rax, cs:__security_cookie
0x180012adb  xor     rax, rsp
0x180012ade  mov     [rbp+57h+var_30], rax
0x180012ae2  movups  xmm0, cs:BLP_TRACELOGGING_INVALID_GUID
0x180012ae9  xor     r15d, r15d
0x180012aec  mov     [rsp+100h+arg_0], rdi
0x180012af4  mov     rdi, r8
0x180012af7  mov     esi, edx
0x180012af9  mov     r14, 0FFFFFFFFFFFFFFFFh
0x180012b00  movups  [rbp+57h+var_A8], xmm0
0x180012b04  test    r8, r8
0x180012b07  jnz     short loc_180012B13
0x180012b09  mov     ebx, 57h ; 'W'
0x180012b0e  jmp     loc_180012B95
0x180012b13  mov     rbx, [r8]
0x180012b16  lea     rcx, ?RpcContextTable@@3U_BR_RPC_CONTEXT_TABLE@@A; _BR_RPC_CONTEXT_TABLE RpcContextTable
0x180012b1d  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180012b23  mov     rcx, rbx; unsigned __int64
0x180012b26  call    ?BrpRpcContextFindWithLockHeld@@YAPEAU_BR_RPC_CONTEXT_ENTRY@@_K@Z; BrpRpcContextFindWithLockHeld(unsigned __int64)
0x180012b2b  mov     rbx, rax
0x180012b2e  test    rax, rax
0x180012b31  jz      short loc_180012B83
0x180012b33  mov     rcx, [rax+20h]; ProcessHandle
0x180012b37  call    ?BrpRpcClientProcessHandleCheck@@YAKPEAX@Z; BrpRpcClientProcessHandleCheck(void *)
0x180012b3c  test    eax, eax
0x180012b3e  jnz     short loc_180012B83
0x180012b40  mov     rdx, rbx
0x180012b43  lea     rcx, xmmword_180028970
0x180012b4a  call    cs:__imp_RtlRbRemoveNode
0x180012b50  lea     rcx, ?RpcContextTable@@3U_BR_RPC_CONTEXT_TABLE@@A; _BR_RPC_CONTEXT_TABLE RpcContextTable
0x180012b57  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180012b5d  mov     rax, [rbx+48h]
0x180012b61  mov     r14, [rbx+50h]
0x180012b65  test    rax, rax
0x180012b68  jz      short loc_180012B71
0x180012b6a  movups  xmm0, xmmword ptr [rax]
0x180012b6d  movups  [rbp+57h+var_A8], xmm0
0x180012b71  mov     edx, esi
0x180012b73  mov     rcx, rbx
0x180012b76  call    ?BrpRpcContextEntryDestroy@@YAXPEAU_BR_RPC_CONTEXT_ENTRY@@W4_BR_EVENT_CALL_REASON@@@Z; BrpRpcContextEntryDestroy(_BR_RPC_CONTEXT_ENTRY *,_BR_EVENT_CALL_REASON)
0x180012b7b  mov     [rdi], r15
0x180012b7e  mov     ebx, r15d
0x180012b81  jmp     short loc_180012B95
0x180012b83  lea     rcx, ?RpcContextTable@@3U_BR_RPC_CONTEXT_TABLE@@A; _BR_RPC_CONTEXT_TABLE RpcContextTable
0x180012b8a  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180012b90  mov     ebx, 6
0x180012b95  mov     eax, cs:dword_180028000
0x180012b9b  mov     rdi, [rsp+100h+arg_0]
0x180012ba3  cmp     eax, 4
0x180012ba6  jbe     loc_180012CA4
0x180012bac  mov     rcx, cs:qword_180028018
0x180012bb3  mov     rax, cs:qword_180028010
0x180012bba  test    al, 1
0x180012bbc  jz      loc_180012CA4
0x180012bc2  mov     rax, rcx
0x180012bc5  and     eax, 1
0x180012bc8  cmp     rax, rcx
0x180012bcb  jnz     loc_180012CA4
0x180012bd1  mov     [rbp+57h+var_D0], sil
0x180012bd5  lea     rax, [rbp+57h+var_D0]
0x180012bd9  mov     [rbp+57h+var_40], rax
0x180012bdd  lea     rcx, _TraceLoggingMetadataEnd
0x180012be4  mov     [rbp+57h+var_CC], ebx
0x180012be7  lea     rax, [rbp+57h+var_CC]
0x180012beb  mov     [rbp+57h+var_50], rax
0x180012bef  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x180012bf3  mov     [rbp+57h+var_C0], r14
0x180012bf7  lea     rax, [rbp+57h+var_A8]
0x180012bfb  mov     [rbp+57h+var_60], rax
0x180012bff  xor     r9d, r9d; RelatedActivityId
0x180012c02  lea     rax, [rbp+57h+var_C0]
0x180012c06  mov     [rbp+57h+var_38], 1
0x180012c0e  mov     [rbp+57h+var_70], rax
0x180012c12  xor     r8d, r8d; ActivityId
0x180012c15  movzx   eax, cs:word_1800223FB
0x180012c1c  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x180012c1f  mov     rax, cs:off_180028008
0x180012c26  mov     [rbp+57h+var_90.Ptr], rax
0x180012c2a  mov     [rbp+57h+var_48], 4
0x180012c32  mov     [rbp+57h+var_58], 10h
0x180012c3a  mov     [rbp+57h+var_68], 8
0x180012c42  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x180012c49  mov     [rbp+57h+EventDescriptor.Keyword], 1
0x180012c51  movzx   eax, word ptr [rax]
0x180012c54  mov     [rbp+57h+var_90.Size], eax
0x180012c57  lea     rax, unk_180022405
0x180012c5e  mov     [rbp+57h+var_80], rax
0x180012c62  lea     rax, _TraceLoggingMetadata
0x180012c69  sub     ecx, eax
0x180012c6b  mov     dword ptr [rbp+57h+var_90.0Ch], 2
0x180012c72  mov     [rbp+57h+var_78], 3Bh ; ';'
0x180012c79  lea     rax, [rbp+57h+var_90]
0x180012c7d  mov     [rbp+57h+var_74], 1
0x180012c84  mov     [rbp+57h+var_C8], ecx
0x180012c87  mov     ecx, [rbp+57h+var_C8]
0x180012c8a  mov     rcx, cs:RegHandle; RegHandle
0x180012c91  mov     [rsp+100h+UserData], rax; UserData
0x180012c96  mov     [rsp+100h+UserDataCount], 6; UserDataCount
0x180012c9e  call    cs:__imp_EventWriteTransfer
0x180012ca4  mov     eax, ebx
0x180012ca6  mov     rcx, [rbp+57h+var_30]
0x180012caa  xor     rcx, rsp; StackCookie
0x180012cad  call    __security_check_cookie
0x180012cb2  add     rsp, 0E0h
0x180012cb9  pop     r15
0x180012cbb  pop     r14
0x180012cbd  pop     rsi
0x180012cbe  pop     rbx
0x180012cbf  pop     rbp
0x180012cc0  retn
```
