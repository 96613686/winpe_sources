# McGenEventWrite_EventWriteTransfer

- ea: `0x18000264c`
- end: `0x1800026a5`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `89`
- prototype: `ULONG __fastcall(__int64, __int64, __int64, __int64, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800026ac`

## callees

- `0x18000264c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000269a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000269a`

## pseudocode

```c
ULONG __fastcall McGenEventWrite_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // rcx
  ULONG v6; // edx

  v5 = (unsigned __int16 *)qword_180013008;
  if ( qword_180013008 )
  {
    UserData->Ptr = qword_180013008;
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
  return EventWriteTransfer(
           MICROSOFT_WINDOWS_DEVICE_DIRECTORY_DEVICE_DIRECTORY_CLIENT_ETW_Context,
           &DEVICE_DIRECTORY_CLIENT_TRACE_EHM_FAILED,
           0,
           0,
           5u,
           UserData);
}

```

## disassembly

```asm
0x18000264c  sub     rsp, 38h
0x180002650  mov     rcx, cs:qword_180013008
0x180002657  mov     rax, [rsp+38h+arg_20]
0x18000265c  test    rcx, rcx
0x18000265f  jnz     short loc_180002668
0x180002661  mov     [rax], rcx
0x180002664  xor     edx, edx
0x180002666  jmp     short loc_180002673
0x180002668  mov     [rax], rcx
0x18000266b  mov     edx, 2
0x180002670  movzx   ecx, word ptr [rcx]
0x180002673  mov     [rax+8], ecx
0x180002676  xor     r9d, r9d; RelatedActivityId
0x180002679  mov     [rax+0Ch], edx
0x18000267c  xor     r8d, r8d; ActivityId
0x18000267f  mov     rcx, cs:MICROSOFT_WINDOWS_DEVICE_DIRECTORY_DEVICE_DIRECTORY_CLIENT_ETW_Context; RegHandle
0x180002686  lea     rdx, DEVICE_DIRECTORY_CLIENT_TRACE_EHM_FAILED; EventDescriptor
0x18000268d  mov     [rsp+38h+UserData], rax; UserData
0x180002692  mov     [rsp+38h+UserDataCount], 5; UserDataCount
0x18000269a  call    cs:__imp_EventWriteTransfer
0x1800026a0  add     rsp, 38h
0x1800026a4  retn
```
