# McGenEventWrite_EventWriteTransfer

- ea: `0x18000342c`
- end: `0x18000347e`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002288`
- `0x1800026f4`
- `0x180002d70`
- `0x180003060`
- `0x180003484`
- `0x1800045f0`

## callees

- `0x18000342c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180003473`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180003473`

## pseudocode

```c
ULONG __fastcall McGenEventWrite_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // rcx
  int v6; // r8d

  v5 = (unsigned __int16 *)qword_18000C008;
  if ( qword_18000C008 )
  {
    UserData->Ptr = qword_18000C008;
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
           ETW_WINDOWS_INTERNAL_SECURITYMITIGATIONBROKER_ETW_CONTROL_GUID_Context,
           a2,
           0,
           0,
           UserDataCount,
           UserData);
}

```

## disassembly

```asm
0x18000342c  sub     rsp, 38h
0x180003430  mov     rcx, cs:qword_18000C008
0x180003437  mov     rax, [rsp+38h+arg_20]
0x18000343c  test    rcx, rcx
0x18000343f  jnz     short loc_180003449
0x180003441  mov     [rax], rcx
0x180003444  xor     r8d, r8d
0x180003447  jmp     short loc_180003455
0x180003449  mov     [rax], rcx
0x18000344c  mov     r8d, 2
0x180003452  movzx   ecx, word ptr [rcx]
0x180003455  mov     [rax+8], ecx
0x180003458  mov     [rax+0Ch], r8d
0x18000345c  xor     r8d, r8d; ActivityId
0x18000345f  mov     rcx, cs:ETW_WINDOWS_INTERNAL_SECURITYMITIGATIONBROKER_ETW_CONTROL_GUID_Context; RegHandle
0x180003466  mov     [rsp+38h+UserData], rax; UserData
0x18000346b  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x180003470  xor     r9d, r9d; RelatedActivityId
0x180003473  call    cs:__imp_EventWriteTransfer
0x180003479  add     rsp, 38h
0x18000347d  retn
```
