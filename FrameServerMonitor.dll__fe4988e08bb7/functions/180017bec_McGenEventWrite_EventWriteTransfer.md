# McGenEventWrite_EventWriteTransfer

- ea: `0x180017bec`
- end: `0x180017c3e`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800127f0`
- `0x180017c44`

## callees

- `0x180017bec`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180017c33`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180017c33`

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

  v5 = (unsigned __int16 *)qword_18005C008;
  if ( qword_18005C008 )
  {
    UserData->Ptr = qword_18005C008;
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
  return EventWriteTransfer(Microsoft_Windows_MF_FrameServer_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x180017bec  sub     rsp, 38h
0x180017bf0  mov     rcx, cs:qword_18005C008
0x180017bf7  mov     rax, [rsp+38h+arg_20]
0x180017bfc  test    rcx, rcx
0x180017bff  jnz     short loc_180017C09
0x180017c01  mov     [rax], rcx
0x180017c04  xor     r8d, r8d
0x180017c07  jmp     short loc_180017C15
0x180017c09  mov     [rax], rcx
0x180017c0c  mov     r8d, 2
0x180017c12  movzx   ecx, word ptr [rcx]
0x180017c15  mov     [rax+8], ecx
0x180017c18  mov     [rax+0Ch], r8d
0x180017c1c  xor     r8d, r8d; ActivityId
0x180017c1f  mov     rcx, cs:Microsoft_Windows_MF_FrameServer_Context; RegHandle
0x180017c26  mov     [rsp+38h+UserData], rax; UserData
0x180017c2b  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x180017c30  xor     r9d, r9d; RelatedActivityId
0x180017c33  call    cs:__imp_EventWriteTransfer
0x180017c39  add     rsp, 38h
0x180017c3d  retn
```
