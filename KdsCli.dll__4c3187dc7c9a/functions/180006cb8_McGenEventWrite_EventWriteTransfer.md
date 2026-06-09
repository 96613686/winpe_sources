# McGenEventWrite_EventWriteTransfer

- ea: `0x180006cb8`
- end: `0x180006d0a`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180004624`
- `0x180004a00`
- `0x180005a24`
- `0x180006d10`
- `0x180007e98`
- `0x1800080e8`

## callees

- `0x180006cb8`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180006cff`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180006cff`

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

  v5 = (unsigned __int16 *)qword_180023008;
  if ( qword_180023008 )
  {
    UserData->Ptr = qword_180023008;
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
  return EventWriteTransfer(KdsSvcOperational_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x180006cb8  sub     rsp, 38h
0x180006cbc  mov     rcx, cs:qword_180023008
0x180006cc3  mov     rax, [rsp+38h+arg_20]
0x180006cc8  test    rcx, rcx
0x180006ccb  jnz     short loc_180006CD5
0x180006ccd  mov     [rax], rcx
0x180006cd0  xor     r8d, r8d
0x180006cd3  jmp     short loc_180006CE1
0x180006cd5  mov     [rax], rcx
0x180006cd8  mov     r8d, 2
0x180006cde  movzx   ecx, word ptr [rcx]
0x180006ce1  mov     [rax+8], ecx
0x180006ce4  mov     [rax+0Ch], r8d
0x180006ce8  xor     r8d, r8d; ActivityId
0x180006ceb  mov     rcx, cs:KdsSvcOperational_Context; RegHandle
0x180006cf2  mov     [rsp+38h+UserData], rax; UserData
0x180006cf7  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x180006cfc  xor     r9d, r9d; RelatedActivityId
0x180006cff  call    cs:__imp_EventWriteTransfer
0x180006d05  add     rsp, 38h
0x180006d09  retn
```
