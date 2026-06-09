# McGenEventWrite_EventWriteTransfer

- ea: `0x140006748`
- end: `0x14000679a`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x1400067a0`
- `0x14000b0d0`
- `0x14000b840`
- `0x14000c3dc`
- `0x14000c45c`
- `0x14000c4f8`
- `0x14000c598`
- `0x14000c668`
- `0x1400113a0`
- `0x140011438`

## callees

- `0x140006748`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x14000678f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x14000678f`

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

  v5 = (unsigned __int16 *)qword_14001D048;
  if ( qword_14001D048 )
  {
    UserData->Ptr = qword_14001D048;
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
  return EventWriteTransfer(WEBAUTH_ETW_CONTROL_GUID_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x140006748  sub     rsp, 38h
0x14000674c  mov     rcx, cs:qword_14001D048
0x140006753  mov     rax, [rsp+38h+arg_20]
0x140006758  test    rcx, rcx
0x14000675b  jnz     short loc_140006765
0x14000675d  mov     [rax], rcx
0x140006760  xor     r8d, r8d
0x140006763  jmp     short loc_140006771
0x140006765  mov     [rax], rcx
0x140006768  mov     r8d, 2
0x14000676e  movzx   ecx, word ptr [rcx]
0x140006771  mov     [rax+8], ecx
0x140006774  mov     [rax+0Ch], r8d
0x140006778  xor     r8d, r8d; ActivityId
0x14000677b  mov     rcx, cs:WEBAUTH_ETW_CONTROL_GUID_Context; RegHandle
0x140006782  mov     [rsp+38h+UserData], rax; UserData
0x140006787  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x14000678c  xor     r9d, r9d; RelatedActivityId
0x14000678f  call    cs:__imp_EventWriteTransfer
0x140006795  add     rsp, 38h
0x140006799  retn
```
