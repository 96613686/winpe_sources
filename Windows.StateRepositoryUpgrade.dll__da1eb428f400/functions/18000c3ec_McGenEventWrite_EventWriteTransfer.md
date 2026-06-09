# McGenEventWrite_EventWriteTransfer

- ea: `0x18000c3ec`
- end: `0x18000c43e`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c444`
- `0x18000c4e0`
- `0x18000c584`
- `0x18000c61c`
- `0x180017f84`
- `0x180028bb8`
- `0x180028c4c`
- `0x180028d98`
- `0x180029008`
- `0x180029120`

## callees

- `0x18000c3ec`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000c433`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000c433`

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

  v5 = (unsigned __int16 *)qword_18004B008;
  if ( qword_18004B008 )
  {
    UserData->Ptr = qword_18004B008;
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
  return EventWriteTransfer(STATEREPOSITORY_ETW_CONTROL_GUID_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x18000c3ec  sub     rsp, 38h
0x18000c3f0  mov     rcx, cs:qword_18004B008
0x18000c3f7  mov     rax, [rsp+38h+arg_20]
0x18000c3fc  test    rcx, rcx
0x18000c3ff  jnz     short loc_18000C409
0x18000c401  mov     [rax], rcx
0x18000c404  xor     r8d, r8d
0x18000c407  jmp     short loc_18000C415
0x18000c409  mov     [rax], rcx
0x18000c40c  mov     r8d, 2
0x18000c412  movzx   ecx, word ptr [rcx]
0x18000c415  mov     [rax+8], ecx
0x18000c418  mov     [rax+0Ch], r8d
0x18000c41c  xor     r8d, r8d; ActivityId
0x18000c41f  mov     rcx, cs:STATEREPOSITORY_ETW_CONTROL_GUID_Context; RegHandle
0x18000c426  mov     [rsp+38h+UserData], rax; UserData
0x18000c42b  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18000c430  xor     r9d, r9d; RelatedActivityId
0x18000c433  call    cs:__imp_EventWriteTransfer
0x18000c439  add     rsp, 38h
0x18000c43d  retn
```
