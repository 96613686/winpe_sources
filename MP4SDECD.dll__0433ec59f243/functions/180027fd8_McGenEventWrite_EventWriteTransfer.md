# McGenEventWrite_EventWriteTransfer

- ea: `0x180027fd8`
- end: `0x18002802a`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180027f28`
- `0x18002e4e4`

## callees

- `0x180027fd8`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002801f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002801f`

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

  v5 = (unsigned __int16 *)qword_180059108;
  if ( qword_180059108 )
  {
    UserData->Ptr = qword_180059108;
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
0x180027fd8  sub     rsp, 38h
0x180027fdc  mov     rcx, cs:qword_180059108
0x180027fe3  mov     rax, [rsp+38h+arg_20]
0x180027fe8  test    rcx, rcx
0x180027feb  jnz     short loc_180027FF5
0x180027fed  mov     [rax], rcx
0x180027ff0  xor     r8d, r8d
0x180027ff3  jmp     short loc_180028001
0x180027ff5  mov     [rax], rcx
0x180027ff8  mov     r8d, 2
0x180027ffe  movzx   ecx, word ptr [rcx]
0x180028001  mov     [rax+8], ecx
0x180028004  mov     [rax+0Ch], r8d
0x180028008  xor     r8d, r8d; ActivityId
0x18002800b  mov     rcx, cs:Microsoft_Windows_MediaFoundation_Performance_Context; RegHandle
0x180028012  mov     [rsp+38h+UserData], rax; UserData
0x180028017  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18002801c  xor     r9d, r9d; RelatedActivityId
0x18002801f  call    cs:__imp_EventWriteTransfer
0x180028025  add     rsp, 38h
0x180028029  retn
```
