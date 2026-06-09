# McGenEventWrite_EventWriteTransfer

- ea: `0x18000fa00`
- end: `0x18000fa52`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, __int64, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000881c`
- `0x18000f718`
- `0x18000f780`
- `0x18000fa58`

## callees

- `0x18000fa00`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000fa47`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000fa47`

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

  v5 = (unsigned __int16 *)qword_18001D048;
  if ( qword_18001D048 )
  {
    UserData->Ptr = qword_18001D048;
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
  return EventWriteTransfer(DIAGNOSTIC_INVOKER_PROVIDER_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x18000fa00  sub     rsp, 38h
0x18000fa04  mov     rcx, cs:qword_18001D048
0x18000fa0b  mov     rax, [rsp+38h+arg_20]
0x18000fa10  test    rcx, rcx
0x18000fa13  jnz     short loc_18000FA1D
0x18000fa15  mov     [rax], rcx
0x18000fa18  xor     r8d, r8d
0x18000fa1b  jmp     short loc_18000FA29
0x18000fa1d  mov     [rax], rcx
0x18000fa20  mov     r8d, 2
0x18000fa26  movzx   ecx, word ptr [rcx]
0x18000fa29  mov     [rax+8], ecx
0x18000fa2c  mov     [rax+0Ch], r8d
0x18000fa30  xor     r8d, r8d; ActivityId
0x18000fa33  mov     rcx, cs:DIAGNOSTIC_INVOKER_PROVIDER_Context; RegHandle
0x18000fa3a  mov     [rsp+38h+UserData], rax; UserData
0x18000fa3f  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18000fa44  xor     r9d, r9d; RelatedActivityId
0x18000fa47  call    cs:__imp_EventWriteTransfer
0x18000fa4d  add     rsp, 38h
0x18000fa51  retn
```
