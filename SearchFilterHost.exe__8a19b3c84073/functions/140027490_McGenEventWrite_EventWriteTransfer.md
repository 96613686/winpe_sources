# McGenEventWrite_EventWriteTransfer

- ea: `0x140027490`
- end: `0x1400274e5`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `85`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400274ec`
- `0x14002ab34`

## callees

- `0x140027490`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1400274da`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1400274da`

## pseudocode

```c
ULONG __fastcall McGenEventWrite_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        __int64 a4,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // rcx
  ULONG v6; // r8d

  v5 = (unsigned __int16 *)qword_14006A0A8;
  if ( qword_14006A0A8 )
  {
    UserData->Ptr = qword_14006A0A8;
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
  return EventWriteTransfer(Microsoft_Windows_Search_Core_Context, a2, 0, 0, 2u, UserData);
}

```

## disassembly

```asm
0x140027490  sub     rsp, 38h
0x140027494  mov     rcx, cs:qword_14006A0A8
0x14002749b  mov     r9d, 2
0x1400274a1  mov     rax, [rsp+38h+arg_20]
0x1400274a6  test    rcx, rcx
0x1400274a9  jnz     short loc_1400274B3
0x1400274ab  mov     [rax], rcx
0x1400274ae  xor     r8d, r8d
0x1400274b1  jmp     short loc_1400274BC
0x1400274b3  mov     [rax], rcx
0x1400274b6  mov     r8d, r9d
0x1400274b9  movzx   ecx, word ptr [rcx]
0x1400274bc  mov     [rax+8], ecx
0x1400274bf  mov     [rax+0Ch], r8d
0x1400274c3  xor     r8d, r8d; ActivityId
0x1400274c6  mov     rcx, cs:Microsoft_Windows_Search_Core_Context; RegHandle
0x1400274cd  mov     [rsp+38h+UserData], rax; UserData
0x1400274d2  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x1400274d7  xor     r9d, r9d; RelatedActivityId
0x1400274da  call    cs:__imp_EventWriteTransfer
0x1400274e0  add     rsp, 38h
0x1400274e4  retn
```
