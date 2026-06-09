# McGenEventWrite_EventWriteTransfer

- ea: `0x18000b1c8`
- end: `0x18000b21a`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180009e8c`
- `0x18000a538`
- `0x18000b220`

## callees

- `0x18000b1c8`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000b20f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000b20f`

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

  v5 = (unsigned __int16 *)qword_180035048;
  if ( qword_180035048 )
  {
    UserData->Ptr = qword_180035048;
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
  return EventWriteTransfer(MICROSOFT_WINDOWS_MOSHOST_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x18000b1c8  sub     rsp, 38h
0x18000b1cc  mov     rcx, cs:qword_180035048
0x18000b1d3  mov     rax, [rsp+38h+arg_20]
0x18000b1d8  test    rcx, rcx
0x18000b1db  jnz     short loc_18000B1E5
0x18000b1dd  mov     [rax], rcx
0x18000b1e0  xor     r8d, r8d
0x18000b1e3  jmp     short loc_18000B1F1
0x18000b1e5  mov     [rax], rcx
0x18000b1e8  mov     r8d, 2
0x18000b1ee  movzx   ecx, word ptr [rcx]
0x18000b1f1  mov     [rax+8], ecx
0x18000b1f4  mov     [rax+0Ch], r8d
0x18000b1f8  xor     r8d, r8d; ActivityId
0x18000b1fb  mov     rcx, cs:MICROSOFT_WINDOWS_MOSHOST_Context; RegHandle
0x18000b202  mov     [rsp+38h+UserData], rax; UserData
0x18000b207  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18000b20c  xor     r9d, r9d; RelatedActivityId
0x18000b20f  call    cs:__imp_EventWriteTransfer
0x18000b215  add     rsp, 38h
0x18000b219  retn
```
