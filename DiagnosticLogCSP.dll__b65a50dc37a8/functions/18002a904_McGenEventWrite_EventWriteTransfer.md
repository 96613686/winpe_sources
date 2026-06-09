# McGenEventWrite_EventWriteTransfer

- ea: `0x18002a904`
- end: `0x18002a95d`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `89`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180028e68`
- `0x180029218`
- `0x18002954c`
- `0x180029bc0`
- `0x18002a964`
- `0x18002a9e8`

## callees

- `0x18002a904`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002a94b`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002a94b`

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

  v5 = (unsigned __int16 *)qword_18004AF28;
  if ( qword_18004AF28 )
  {
    UserData->Ptr = qword_18004AF28;
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
  return EventWriteTransfer(Microsoft_Windows_XPerfCore_ETWProvider_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x18002a904  sub     rsp, 38h
0x18002a908  mov     rcx, cs:qword_18004AF28
0x18002a90f  mov     rax, [rsp+38h+arg_20]
0x18002a914  test    rcx, rcx
0x18002a917  jnz     short loc_18002A921
0x18002a919  mov     [rax], rcx
0x18002a91c  xor     r8d, r8d
0x18002a91f  jmp     short loc_18002A92D
0x18002a921  mov     [rax], rcx
0x18002a924  mov     r8d, 2
0x18002a92a  movzx   ecx, word ptr [rcx]
0x18002a92d  mov     [rax+8], ecx
0x18002a930  mov     [rax+0Ch], r8d
0x18002a934  xor     r8d, r8d; ActivityId
0x18002a937  mov     rcx, cs:Microsoft_Windows_XPerfCore_ETWProvider_Context; RegHandle
0x18002a93e  mov     [rsp+38h+UserData], rax; UserData
0x18002a943  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18002a948  xor     r9d, r9d; RelatedActivityId
0x18002a94b  call    cs:__imp_EventWriteTransfer
0x18002a952  nop     dword ptr [rax+rax+00h]
0x18002a957  add     rsp, 38h
0x18002a95b  retn
```
