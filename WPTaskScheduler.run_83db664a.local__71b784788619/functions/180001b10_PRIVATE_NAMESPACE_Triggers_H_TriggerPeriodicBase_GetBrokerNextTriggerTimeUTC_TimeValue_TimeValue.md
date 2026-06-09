# PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase::GetBrokerNextTriggerTimeUTC(TimeValue &,TimeValue &)

- ea: `0x180001b10`
- end: `0x180001bc9`
- name: `?GetBrokerNextTriggerTimeUTC@TriggerPeriodicBase@PRIVATE_NAMESPACE_Triggers_H@@AEAAJAEAVTimeValue@@0@Z`
- size: `185`
- prototype: `int(PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase *__hidden this, struct TimeValue *, struct TimeValue *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001360`
- `0x18000de40`

## callees

- `0x180001b10`

## import_xrefs

- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180001b62`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180001b93`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180001b62`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180001b93`
- `TimeBrokerClient!TbQueryCEventTriggerTime` at `0x180001b41`
- `TimeBrokerClient!TbQueryCEventTriggerTime` at `0x180001b41`

## pseudocode

```c
__int64 __fastcall PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase::GetBrokerNextTriggerTimeUTC(
        PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase *this,
        struct TimeValue *a2,
        struct TimeValue *a3)
{
  __int64 v3; // rcx
  __int64 result; // rax
  unsigned int v7; // ebp
  __int64 v8; // [rsp+40h] [rbp+8h] BYREF
  __int64 v9; // [rsp+58h] [rbp+20h] BYREF

  v3 = *((_QWORD *)this + 52);
  v8 = 0;
  v9 = 0;
  result = TbQueryCEventTriggerTime(v3, &v8, &v9);
  v7 = result;
  if ( (int)result >= 0 )
  {
    *((_QWORD *)a2 + 2) = v8;
    if ( FileTimeToSystemTime((const FILETIME *)a2 + 2, (LPSYSTEMTIME)a2) )
    {
      *((_DWORD *)a2 + 7) = *((_DWORD *)a2 + 5);
      *((_DWORD *)a2 + 6) = *((_DWORD *)a2 + 4);
      *((_QWORD *)a2 + 4) = 0;
      *((_DWORD *)a2 + 10) = 1;
    }
    *((_QWORD *)a3 + 2) = v9;
    if ( FileTimeToSystemTime((const FILETIME *)a3 + 2, (LPSYSTEMTIME)a3) )
    {
      *((_DWORD *)a3 + 7) = *((_DWORD *)a3 + 5);
      *((_DWORD *)a3 + 6) = *((_DWORD *)a3 + 4);
      *((_QWORD *)a3 + 4) = 0;
      *((_DWORD *)a3 + 10) = 1;
    }
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x180001b10  mov     [rsp+arg_10], rbx
0x180001b15  push    rbp
0x180001b16  push    rdi
0x180001b17  push    r14
0x180001b19  sub     rsp, 20h
0x180001b1d  mov     rcx, [rcx+1A0h]
0x180001b24  mov     rbx, r8
0x180001b27  mov     rdi, rdx
0x180001b2a  lea     r8, [rsp+38h+arg_18]
0x180001b2f  xor     r14d, r14d
0x180001b32  lea     rdx, [rsp+38h+arg_0]
0x180001b37  mov     [rsp+38h+arg_0], r14
0x180001b3c  mov     [rsp+38h+arg_18], r14
0x180001b41  call    cs:__imp_TbQueryCEventTriggerTime
0x180001b47  mov     ebp, eax
0x180001b49  test    eax, eax
0x180001b4b  js      short loc_180001BBB
0x180001b4d  mov     rcx, [rsp+38h+arg_0]
0x180001b52  mov     rdx, rdi; lpSystemTime
0x180001b55  mov     [rdi+10h], rcx
0x180001b59  lea     rcx, [rdi+10h]; lpFileTime
0x180001b5d  mov     [rsp+38h+arg_8], rsi
0x180001b62  call    cs:__imp_FileTimeToSystemTime
0x180001b68  test    eax, eax
0x180001b6a  jz      short loc_180001B83
0x180001b6c  mov     eax, [rdi+14h]
0x180001b6f  mov     [rdi+1Ch], eax
0x180001b72  mov     eax, [rdi+10h]
0x180001b75  mov     [rdi+18h], eax
0x180001b78  mov     [rdi+20h], r14
0x180001b7c  mov     dword ptr [rdi+28h], 1
0x180001b83  mov     rax, [rsp+38h+arg_18]
0x180001b88  lea     rcx, [rbx+10h]; lpFileTime
0x180001b8c  mov     rdx, rbx; lpSystemTime
0x180001b8f  mov     [rbx+10h], rax
0x180001b93  call    cs:__imp_FileTimeToSystemTime
0x180001b99  mov     rsi, [rsp+38h+arg_8]
0x180001b9e  test    eax, eax
0x180001ba0  jz      short loc_180001BB9
0x180001ba2  mov     eax, [rbx+14h]
0x180001ba5  mov     [rbx+1Ch], eax
0x180001ba8  mov     eax, [rbx+10h]
0x180001bab  mov     [rbx+18h], eax
0x180001bae  mov     [rbx+20h], r14
0x180001bb2  mov     dword ptr [rbx+28h], 1
0x180001bb9  mov     eax, ebp
0x180001bbb  mov     rbx, [rsp+38h+arg_10]
0x180001bc0  add     rsp, 20h
0x180001bc4  pop     r14
0x180001bc6  pop     rdi
0x180001bc7  pop     rbp
0x180001bc8  retn
```
