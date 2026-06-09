# McGenEventWrite_EventWriteTransfer

- ea: `0x180014098`
- end: `0x1800140ed`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `85`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000fa10`
- `0x1800140f4`
- `0x180014168`

## callees

- `0x180014098`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800140e2`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800140e2`

## pseudocode

```c
ULONG __fastcall McGenEventWrite_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        __int64 a4,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // rcx
  ULONG v6; // r8d

  v5 = (unsigned __int16 *)qword_180026018;
  if ( qword_180026018 )
  {
    UserData->Ptr = qword_180026018;
    v6 = 2;
    LODWORD(v5) = *v5;
  }
  else
  {
    UserData->Ptr = 0;
    v6 = 0;
  }
  UserData->Size = (unsigned int)v5;
  UserData->Reserved = v6;
  return EventWriteTransfer(TimeBrokerEtwGuid_Context, a2, 0, 0, 4u, UserData);
}

```

## disassembly

```asm
0x180014098  sub     rsp, 38h
0x18001409c  mov     rcx, cs:qword_180026018
0x1800140a3  mov     rax, [rsp+38h+arg_20]
0x1800140a8  test    rcx, rcx
0x1800140ab  jnz     short loc_1800140B5
0x1800140ad  mov     [rax], rcx
0x1800140b0  xor     r8d, r8d
0x1800140b3  jmp     short loc_1800140C1
0x1800140b5  mov     [rax], rcx
0x1800140b8  mov     r8d, 2
0x1800140be  movzx   ecx, word ptr [rcx]
0x1800140c1  mov     [rax+8], ecx
0x1800140c4  xor     r9d, r9d; RelatedActivityId
0x1800140c7  mov     [rax+0Ch], r8d
0x1800140cb  xor     r8d, r8d; ActivityId
0x1800140ce  mov     rcx, cs:TimeBrokerEtwGuid_Context; RegHandle
0x1800140d5  mov     [rsp+38h+UserData], rax; UserData
0x1800140da  mov     [rsp+38h+UserDataCount], 4; UserDataCount
0x1800140e2  call    cs:__imp_EventWriteTransfer
0x1800140e8  add     rsp, 38h
0x1800140ec  retn
```
