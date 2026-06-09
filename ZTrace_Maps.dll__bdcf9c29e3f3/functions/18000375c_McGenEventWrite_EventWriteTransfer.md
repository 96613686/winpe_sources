# McGenEventWrite_EventWriteTransfer

- ea: `0x18000375c`
- end: `0x1800037ae`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, __int64, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800037b4`
- `0x180003854`
- `0x18000390c`
- `0x1800039d4`

## callees

- `0x18000375c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800037a3`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800037a3`

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

  v5 = (unsigned __int16 *)qword_180007048;
  if ( qword_180007048 )
  {
    UserData->Ptr = qword_180007048;
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
  return EventWriteTransfer(MICROSOFT_WINDOWS_ZTRACEMAPS_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x18000375c  sub     rsp, 38h
0x180003760  mov     rcx, cs:qword_180007048
0x180003767  mov     rax, [rsp+38h+arg_20]
0x18000376c  test    rcx, rcx
0x18000376f  jnz     short loc_180003779
0x180003771  mov     [rax], rcx
0x180003774  xor     r8d, r8d
0x180003777  jmp     short loc_180003785
0x180003779  mov     [rax], rcx
0x18000377c  mov     r8d, 2
0x180003782  movzx   ecx, word ptr [rcx]
0x180003785  mov     [rax+8], ecx
0x180003788  mov     [rax+0Ch], r8d
0x18000378c  xor     r8d, r8d; ActivityId
0x18000378f  mov     rcx, cs:MICROSOFT_WINDOWS_ZTRACEMAPS_Context; RegHandle
0x180003796  mov     [rsp+38h+UserData], rax; UserData
0x18000379b  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x1800037a0  xor     r9d, r9d; RelatedActivityId
0x1800037a3  call    cs:__imp_EventWriteTransfer
0x1800037a9  add     rsp, 38h
0x1800037ad  retn
```
