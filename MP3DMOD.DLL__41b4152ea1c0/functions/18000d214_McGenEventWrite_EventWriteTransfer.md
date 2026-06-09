# McGenEventWrite_EventWriteTransfer

- ea: `0x18000d214`
- end: `0x18000d266`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000d164`
- `0x18000fcc8`

## callees

- `0x18000d214`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000d25b`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000d25b`

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

  v5 = (unsigned __int16 *)qword_18001B028;
  if ( qword_18001B028 )
  {
    UserData->Ptr = qword_18001B028;
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
  return EventWriteTransfer(Microsoft_Windows_MediaFoundation_Performance_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x18000d214  sub     rsp, 38h
0x18000d218  mov     rcx, cs:qword_18001B028
0x18000d21f  mov     rax, [rsp+38h+arg_20]
0x18000d224  test    rcx, rcx
0x18000d227  jnz     short loc_18000D231
0x18000d229  mov     [rax], rcx
0x18000d22c  xor     r8d, r8d
0x18000d22f  jmp     short loc_18000D23D
0x18000d231  mov     [rax], rcx
0x18000d234  mov     r8d, 2
0x18000d23a  movzx   ecx, word ptr [rcx]
0x18000d23d  mov     [rax+8], ecx
0x18000d240  mov     [rax+0Ch], r8d
0x18000d244  xor     r8d, r8d; ActivityId
0x18000d247  mov     rcx, cs:Microsoft_Windows_MediaFoundation_Performance_Context; RegHandle
0x18000d24e  mov     [rsp+38h+UserData], rax; UserData
0x18000d253  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18000d258  xor     r9d, r9d; RelatedActivityId
0x18000d25b  call    cs:__imp_EventWriteTransfer
0x18000d261  add     rsp, 38h
0x18000d265  retn
```
