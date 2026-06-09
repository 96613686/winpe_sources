# McGenEventWrite_EventWriteTransfer

- ea: `0x1800087b0`
- end: `0x180008802`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800023a0`
- `0x1800026f0`
- `0x180008808`

## callees

- `0x1800087b0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800087f7`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800087f7`

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

  v5 = (unsigned __int16 *)qword_180027088;
  if ( qword_180027088 )
  {
    UserData->Ptr = qword_180027088;
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
0x1800087b0  sub     rsp, 38h
0x1800087b4  mov     rcx, cs:qword_180027088
0x1800087bb  mov     rax, [rsp+38h+arg_20]
0x1800087c0  test    rcx, rcx
0x1800087c3  jnz     short loc_1800087CD
0x1800087c5  mov     [rax], rcx
0x1800087c8  xor     r8d, r8d
0x1800087cb  jmp     short loc_1800087D9
0x1800087cd  mov     [rax], rcx
0x1800087d0  mov     r8d, 2
0x1800087d6  movzx   ecx, word ptr [rcx]
0x1800087d9  mov     [rax+8], ecx
0x1800087dc  mov     [rax+0Ch], r8d
0x1800087e0  xor     r8d, r8d; ActivityId
0x1800087e3  mov     rcx, cs:Microsoft_Windows_MediaFoundation_Performance_Context; RegHandle
0x1800087ea  mov     [rsp+38h+UserData], rax; UserData
0x1800087ef  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x1800087f4  xor     r9d, r9d; RelatedActivityId
0x1800087f7  call    cs:__imp_EventWriteTransfer
0x1800087fd  add     rsp, 38h
0x180008801  retn
```
