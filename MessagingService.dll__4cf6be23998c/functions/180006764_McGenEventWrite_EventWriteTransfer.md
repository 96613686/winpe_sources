# McGenEventWrite_EventWriteTransfer

- ea: `0x180006764`
- end: `0x1800067b6`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, __int64, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180005d98`
- `0x180005fe8`
- `0x1800067bc`

## callees

- `0x180006764`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800067ab`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800067ab`

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

  v5 = (unsigned __int16 *)qword_180013058;
  if ( qword_180013058 )
  {
    UserData->Ptr = qword_180013058;
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
  return EventWriteTransfer(MICROSOFT_WINDOWS_USERDATAACCESS_USERDATAUTILS_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x180006764  sub     rsp, 38h
0x180006768  mov     rcx, cs:qword_180013058
0x18000676f  mov     rax, [rsp+38h+arg_20]
0x180006774  test    rcx, rcx
0x180006777  jnz     short loc_180006781
0x180006779  mov     [rax], rcx
0x18000677c  xor     r8d, r8d
0x18000677f  jmp     short loc_18000678D
0x180006781  mov     [rax], rcx
0x180006784  mov     r8d, 2
0x18000678a  movzx   ecx, word ptr [rcx]
0x18000678d  mov     [rax+8], ecx
0x180006790  mov     [rax+0Ch], r8d
0x180006794  xor     r8d, r8d; ActivityId
0x180006797  mov     rcx, cs:MICROSOFT_WINDOWS_USERDATAACCESS_USERDATAUTILS_Context; RegHandle
0x18000679e  mov     [rsp+38h+UserData], rax; UserData
0x1800067a3  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x1800067a8  xor     r9d, r9d; RelatedActivityId
0x1800067ab  call    cs:__imp_EventWriteTransfer
0x1800067b1  add     rsp, 38h
0x1800067b5  retn
```
