# McGenEventWrite_EventWriteTransfer

- ea: `0x180006f28`
- end: `0x180006f7a`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, __int64, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180006f80`
- `0x180007018`
- `0x180007518`
- `0x180008390`

## callees

- `0x180006f28`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180006f6f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180006f6f`

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

  v5 = (unsigned __int16 *)qword_180013048;
  if ( qword_180013048 )
  {
    UserData->Ptr = qword_180013048;
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
0x180006f28  sub     rsp, 38h
0x180006f2c  mov     rcx, cs:qword_180013048
0x180006f33  mov     rax, [rsp+38h+arg_20]
0x180006f38  test    rcx, rcx
0x180006f3b  jnz     short loc_180006F45
0x180006f3d  mov     [rax], rcx
0x180006f40  xor     r8d, r8d
0x180006f43  jmp     short loc_180006F51
0x180006f45  mov     [rax], rcx
0x180006f48  mov     r8d, 2
0x180006f4e  movzx   ecx, word ptr [rcx]
0x180006f51  mov     [rax+8], ecx
0x180006f54  mov     [rax+0Ch], r8d
0x180006f58  xor     r8d, r8d; ActivityId
0x180006f5b  mov     rcx, cs:Microsoft_Windows_LiveId_Context; RegHandle
0x180006f62  mov     [rsp+38h+UserData], rax; UserData
0x180006f67  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x180006f6c  xor     r9d, r9d; RelatedActivityId
0x180006f6f  call    cs:__imp_EventWriteTransfer
0x180006f75  add     rsp, 38h
0x180006f79  retn
```
