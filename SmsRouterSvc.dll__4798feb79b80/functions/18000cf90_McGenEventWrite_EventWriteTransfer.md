# McGenEventWrite_EventWriteTransfer

- ea: `0x18000cf90`
- end: `0x18000cfe2`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `11`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000c694`
- `0x18000cc20`
- `0x18001c538`
- `0x180021a10`
- `0x180039ab4`
- `0x18003bc3c`
- `0x18004c7b4`
- `0x18004cf34`
- `0x18004eea4`
- `0x18004ef50`
- `0x180051628`

## callees

- `0x18000cf90`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000cfd7`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000cfd7`

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

  v5 = (unsigned __int16 *)qword_18008C008;
  if ( qword_18008C008 )
  {
    UserData->Ptr = qword_18008C008;
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
  return EventWriteTransfer(Microsoft_Windows_CoreSystem_SmsRouter_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x18000cf90  sub     rsp, 38h
0x18000cf94  mov     rcx, cs:qword_18008C008
0x18000cf9b  mov     rax, [rsp+38h+arg_20]
0x18000cfa0  test    rcx, rcx
0x18000cfa3  jnz     short loc_18000CFAD
0x18000cfa5  mov     [rax], rcx
0x18000cfa8  xor     r8d, r8d
0x18000cfab  jmp     short loc_18000CFB9
0x18000cfad  mov     [rax], rcx
0x18000cfb0  mov     r8d, 2
0x18000cfb6  movzx   ecx, word ptr [rcx]
0x18000cfb9  mov     [rax+8], ecx
0x18000cfbc  mov     [rax+0Ch], r8d
0x18000cfc0  xor     r8d, r8d; ActivityId
0x18000cfc3  mov     rcx, cs:Microsoft_Windows_CoreSystem_SmsRouter_Context; RegHandle
0x18000cfca  mov     [rsp+38h+UserData], rax; UserData
0x18000cfcf  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18000cfd4  xor     r9d, r9d; RelatedActivityId
0x18000cfd7  call    cs:__imp_EventWriteTransfer
0x18000cfdd  add     rsp, 38h
0x18000cfe1  retn
```
