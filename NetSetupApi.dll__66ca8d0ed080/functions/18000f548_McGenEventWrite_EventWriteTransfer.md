# McGenEventWrite_EventWriteTransfer

- ea: `0x18000f548`
- end: `0x18000f59a`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, __int64, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18000f5a0`
- `0x18000f608`

## callees

- `0x18000f548`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000f58f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000f58f`

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

  v5 = (unsigned __int16 *)qword_180025028;
  if ( qword_180025028 )
  {
    UserData->Ptr = qword_180025028;
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
  return EventWriteTransfer(NETSETUP_ETW_GUID_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x18000f548  sub     rsp, 38h
0x18000f54c  mov     rcx, cs:qword_180025028
0x18000f553  mov     rax, [rsp+38h+arg_20]
0x18000f558  test    rcx, rcx
0x18000f55b  jnz     short loc_18000F565
0x18000f55d  mov     [rax], rcx
0x18000f560  xor     r8d, r8d
0x18000f563  jmp     short loc_18000F571
0x18000f565  mov     [rax], rcx
0x18000f568  mov     r8d, 2
0x18000f56e  movzx   ecx, word ptr [rcx]
0x18000f571  mov     [rax+8], ecx
0x18000f574  mov     [rax+0Ch], r8d
0x18000f578  xor     r8d, r8d; ActivityId
0x18000f57b  mov     rcx, cs:NETSETUP_ETW_GUID_Context; RegHandle
0x18000f582  mov     [rsp+38h+UserData], rax; UserData
0x18000f587  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18000f58c  xor     r9d, r9d; RelatedActivityId
0x18000f58f  call    cs:__imp_EventWriteTransfer
0x18000f595  add     rsp, 38h
0x18000f599  retn
```
