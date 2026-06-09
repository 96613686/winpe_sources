# McGenEventWrite_EventWriteTransfer

- ea: `0x1800076e0`
- end: `0x180007732`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180007740`
- `0x18000a6d4`
- `0x18000affc`
- `0x18000b120`
- `0x18000f4b0`

## callees

- `0x1800076e0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180007727`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180007727`

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

  v5 = (unsigned __int16 *)qword_180049048;
  if ( qword_180049048 )
  {
    UserData->Ptr = qword_180049048;
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
0x1800076e0  sub     rsp, 38h
0x1800076e4  mov     rcx, cs:qword_180049048
0x1800076eb  mov     rax, [rsp+38h+arg_20]
0x1800076f0  test    rcx, rcx
0x1800076f3  jnz     short loc_1800076FD
0x1800076f5  mov     [rax], rcx
0x1800076f8  xor     r8d, r8d
0x1800076fb  jmp     short loc_180007709
0x1800076fd  mov     [rax], rcx
0x180007700  mov     r8d, 2
0x180007706  movzx   ecx, word ptr [rcx]
0x180007709  mov     [rax+8], ecx
0x18000770c  mov     [rax+0Ch], r8d
0x180007710  xor     r8d, r8d; ActivityId
0x180007713  mov     rcx, cs:NETSETUP_ETW_GUID_Context; RegHandle
0x18000771a  mov     [rsp+38h+UserData], rax; UserData
0x18000771f  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x180007724  xor     r9d, r9d; RelatedActivityId
0x180007727  call    cs:__imp_EventWriteTransfer
0x18000772d  add     rsp, 38h
0x180007731  retn
```
