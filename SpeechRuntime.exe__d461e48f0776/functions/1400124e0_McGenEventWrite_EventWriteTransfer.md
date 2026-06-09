# McGenEventWrite_EventWriteTransfer

- ea: `0x1400124e0`
- end: `0x140012535`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `85`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14001253c`

## callees

- `0x1400124e0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x14001252a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x14001252a`

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

  v5 = (unsigned __int16 *)qword_14004C0B8;
  if ( qword_14004C0B8 )
  {
    UserData->Ptr = qword_14004C0B8;
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
  return EventWriteTransfer(PUBLISHER_WINDOWSPHONE_SPEECH_Context, a2, 0, 0, 2u, UserData);
}

```

## disassembly

```asm
0x1400124e0  sub     rsp, 38h
0x1400124e4  mov     rcx, cs:qword_14004C0B8
0x1400124eb  mov     r9d, 2
0x1400124f1  mov     rax, [rsp+38h+arg_20]
0x1400124f6  test    rcx, rcx
0x1400124f9  jnz     short loc_140012503
0x1400124fb  mov     [rax], rcx
0x1400124fe  xor     r8d, r8d
0x140012501  jmp     short loc_14001250C
0x140012503  mov     [rax], rcx
0x140012506  mov     r8d, r9d
0x140012509  movzx   ecx, word ptr [rcx]
0x14001250c  mov     [rax+8], ecx
0x14001250f  mov     [rax+0Ch], r8d
0x140012513  xor     r8d, r8d; ActivityId
0x140012516  mov     rcx, cs:PUBLISHER_WINDOWSPHONE_SPEECH_Context; RegHandle
0x14001251d  mov     [rsp+38h+UserData], rax; UserData
0x140012522  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x140012527  xor     r9d, r9d; RelatedActivityId
0x14001252a  call    cs:__imp_EventWriteTransfer
0x140012530  add     rsp, 38h
0x140012534  retn
```
