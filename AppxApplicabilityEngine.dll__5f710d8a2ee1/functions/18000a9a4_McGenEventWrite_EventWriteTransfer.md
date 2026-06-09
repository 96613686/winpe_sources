# McGenEventWrite_EventWriteTransfer

- ea: `0x18000a9a4`
- end: `0x18000a9f6`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800098c0`
- `0x18000a948`
- `0x18000b528`
- `0x18000cef0`
- `0x18000d510`
- `0x18000db80`

## callees

- `0x18000a9a4`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000a9eb`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000a9eb`

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

  v5 = (unsigned __int16 *)qword_180039008;
  if ( qword_180039008 )
  {
    UserData->Ptr = qword_180039008;
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
  return EventWriteTransfer(ApplicabilityEngine_ETW_Provider_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x18000a9a4  sub     rsp, 38h
0x18000a9a8  mov     rcx, cs:qword_180039008
0x18000a9af  mov     rax, [rsp+38h+arg_20]
0x18000a9b4  test    rcx, rcx
0x18000a9b7  jnz     short loc_18000A9C1
0x18000a9b9  mov     [rax], rcx
0x18000a9bc  xor     r8d, r8d
0x18000a9bf  jmp     short loc_18000A9CD
0x18000a9c1  mov     [rax], rcx
0x18000a9c4  mov     r8d, 2
0x18000a9ca  movzx   ecx, word ptr [rcx]
0x18000a9cd  mov     [rax+8], ecx
0x18000a9d0  mov     [rax+0Ch], r8d
0x18000a9d4  xor     r8d, r8d; ActivityId
0x18000a9d7  mov     rcx, cs:ApplicabilityEngine_ETW_Provider_Context; RegHandle
0x18000a9de  mov     [rsp+38h+UserData], rax; UserData
0x18000a9e3  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18000a9e8  xor     r9d, r9d; RelatedActivityId
0x18000a9eb  call    cs:__imp_EventWriteTransfer
0x18000a9f1  add     rsp, 38h
0x18000a9f5  retn
```
