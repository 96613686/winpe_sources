# McGenEventWrite_EventWriteTransfer

- ea: `0x14000f9b0`
- end: `0x14000fa02`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, __int64, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000afe0`
- `0x14000fef0`
- `0x140010050`

## callees

- `0x14000f9b0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x14000f9f7`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x14000f9f7`

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

  v5 = (unsigned __int16 *)qword_14001B0F8;
  if ( qword_14001B0F8 )
  {
    UserData->Ptr = qword_14001B0F8;
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
  return EventWriteTransfer(SPELL_CHECKING_HOST_ETW_PROVIDER_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x14000f9b0  sub     rsp, 38h
0x14000f9b4  mov     rcx, cs:qword_14001B0F8
0x14000f9bb  mov     rax, [rsp+38h+arg_20]
0x14000f9c0  test    rcx, rcx
0x14000f9c3  jnz     short loc_14000F9CD
0x14000f9c5  mov     [rax], rcx
0x14000f9c8  xor     r8d, r8d
0x14000f9cb  jmp     short loc_14000F9D9
0x14000f9cd  mov     [rax], rcx
0x14000f9d0  mov     r8d, 2
0x14000f9d6  movzx   ecx, word ptr [rcx]
0x14000f9d9  mov     [rax+8], ecx
0x14000f9dc  mov     [rax+0Ch], r8d
0x14000f9e0  xor     r8d, r8d; ActivityId
0x14000f9e3  mov     rcx, cs:SPELL_CHECKING_HOST_ETW_PROVIDER_Context; RegHandle
0x14000f9ea  mov     [rsp+38h+UserData], rax; UserData
0x14000f9ef  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x14000f9f4  xor     r9d, r9d; RelatedActivityId
0x14000f9f7  call    cs:__imp_EventWriteTransfer
0x14000f9fd  add     rsp, 38h
0x14000fa01  retn
```
