# McGenEventWrite_EventWriteTransfer

- ea: `0x18000c7f4`
- end: `0x18000c846`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000c84c`
- `0x18000c8e4`
- `0x180026b50`
- `0x180026c20`
- `0x180026d3c`

## callees

- `0x18000c7f4`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000c83b`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000c83b`

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

  v5 = (unsigned __int16 *)qword_18004D008;
  if ( qword_18004D008 )
  {
    UserData->Ptr = qword_18004D008;
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
  return EventWriteTransfer(Microsoft_Windows_LiveId_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x18000c7f4  sub     rsp, 38h
0x18000c7f8  mov     rcx, cs:qword_18004D008
0x18000c7ff  mov     rax, [rsp+38h+arg_20]
0x18000c804  test    rcx, rcx
0x18000c807  jnz     short loc_18000C811
0x18000c809  mov     [rax], rcx
0x18000c80c  xor     r8d, r8d
0x18000c80f  jmp     short loc_18000C81D
0x18000c811  mov     [rax], rcx
0x18000c814  mov     r8d, 2
0x18000c81a  movzx   ecx, word ptr [rcx]
0x18000c81d  mov     [rax+8], ecx
0x18000c820  mov     [rax+0Ch], r8d
0x18000c824  xor     r8d, r8d; ActivityId
0x18000c827  mov     rcx, cs:Microsoft_Windows_LiveId_Context; RegHandle
0x18000c82e  mov     [rsp+38h+UserData], rax; UserData
0x18000c833  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18000c838  xor     r9d, r9d; RelatedActivityId
0x18000c83b  call    cs:__imp_EventWriteTransfer
0x18000c841  add     rsp, 38h
0x18000c845  retn
```
