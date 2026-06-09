# McGenEventWrite_EventWriteTransfer

- ea: `0x180007120`
- end: `0x180007172`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, __int64, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180006670`
- `0x180006ad0`
- `0x180009b0c`

## callees

- `0x180007120`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180007167`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180007167`

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

  v5 = (unsigned __int16 *)qword_18002B048;
  if ( qword_18002B048 )
  {
    UserData->Ptr = qword_18002B048;
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
  return EventWriteTransfer(SCDEVICEENUM_PROVIDER_GUID_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x180007120  sub     rsp, 38h
0x180007124  mov     rcx, cs:qword_18002B048
0x18000712b  mov     rax, [rsp+38h+arg_20]
0x180007130  test    rcx, rcx
0x180007133  jnz     short loc_18000713D
0x180007135  mov     [rax], rcx
0x180007138  xor     r8d, r8d
0x18000713b  jmp     short loc_180007149
0x18000713d  mov     [rax], rcx
0x180007140  mov     r8d, 2
0x180007146  movzx   ecx, word ptr [rcx]
0x180007149  mov     [rax+8], ecx
0x18000714c  mov     [rax+0Ch], r8d
0x180007150  xor     r8d, r8d; ActivityId
0x180007153  mov     rcx, cs:SCDEVICEENUM_PROVIDER_GUID_Context; RegHandle
0x18000715a  mov     [rsp+38h+UserData], rax; UserData
0x18000715f  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x180007164  xor     r9d, r9d; RelatedActivityId
0x180007167  call    cs:__imp_EventWriteTransfer
0x18000716d  add     rsp, 38h
0x180007171  retn
```
