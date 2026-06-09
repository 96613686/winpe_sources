# McGenEventWrite_EventWriteTransfer

- ea: `0x18001bc04`
- end: `0x18001bc59`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `85`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180007a70`
- `0x1800134a0`

## callees

- `0x18001bc04`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001bc4e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001bc4e`

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

  v5 = (unsigned __int16 *)qword_180040178;
  if ( qword_180040178 )
  {
    UserData->Ptr = qword_180040178;
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
  return EventWriteTransfer(MS_EaseOfAccess_Provider_Context, a2, 0, 0, 1u, UserData);
}

```

## disassembly

```asm
0x18001bc04  sub     rsp, 38h
0x18001bc08  mov     rcx, cs:qword_180040178
0x18001bc0f  mov     rax, [rsp+38h+arg_20]
0x18001bc14  test    rcx, rcx
0x18001bc17  jnz     short loc_18001BC21
0x18001bc19  mov     [rax], rcx
0x18001bc1c  xor     r8d, r8d
0x18001bc1f  jmp     short loc_18001BC2D
0x18001bc21  mov     [rax], rcx
0x18001bc24  mov     r8d, 2
0x18001bc2a  movzx   ecx, word ptr [rcx]
0x18001bc2d  mov     [rax+8], ecx
0x18001bc30  xor     r9d, r9d; RelatedActivityId
0x18001bc33  mov     [rax+0Ch], r8d
0x18001bc37  xor     r8d, r8d; ActivityId
0x18001bc3a  mov     rcx, cs:MS_EaseOfAccess_Provider_Context; RegHandle
0x18001bc41  mov     [rsp+38h+UserData], rax; UserData
0x18001bc46  mov     [rsp+38h+UserDataCount], 1; UserDataCount
0x18001bc4e  call    cs:__imp_EventWriteTransfer
0x18001bc54  add     rsp, 38h
0x18001bc58  retn
```
