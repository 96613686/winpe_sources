# McGenEventWrite_EventWriteTransfer

- ea: `0x18000b448`
- end: `0x18000b495`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `77`
- prototype: `ULONG __fastcall(REGHANDLE *, const EVENT_DESCRIPTOR *, __int64, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180007ef0`
- `0x180008360`
- `0x180008950`
- `0x18000aebc`
- `0x18000b08c`
- `0x180019cc0`
- `0x180019d98`

## callees

- `0x18000b448`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000b48a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000b48a`

## pseudocode

```c
ULONG __fastcall McGenEventWrite_EventWriteTransfer(
        REGHANDLE *a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // r8
  int v6; // r10d

  v5 = (unsigned __int16 *)a1[1];
  if ( v5 )
  {
    UserData->Ptr = (ULONGLONG)v5;
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
  return EventWriteTransfer(*a1, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x18000b448  sub     rsp, 38h
0x18000b44c  mov     r8, [rcx+8]
0x18000b450  mov     rax, [rsp+38h+arg_20]
0x18000b455  test    r8, r8
0x18000b458  jnz     short loc_18000B462
0x18000b45a  mov     [rax], r8
0x18000b45d  xor     r10d, r10d
0x18000b460  jmp     short loc_18000B46F
0x18000b462  mov     [rax], r8
0x18000b465  mov     r10d, 2
0x18000b46b  movzx   r8d, word ptr [r8]
0x18000b46f  mov     [rax+8], r8d
0x18000b473  xor     r8d, r8d; ActivityId
0x18000b476  mov     [rsp+38h+UserData], rax; UserData
0x18000b47b  mov     [rax+0Ch], r10d
0x18000b47f  mov     rcx, [rcx]; RegHandle
0x18000b482  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18000b487  xor     r9d, r9d; RelatedActivityId
0x18000b48a  call    cs:__imp_EventWriteTransfer
0x18000b490  add     rsp, 38h
0x18000b494  retn
```
