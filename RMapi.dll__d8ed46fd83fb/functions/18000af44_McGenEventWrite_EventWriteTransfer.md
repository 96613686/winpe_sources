# McGenEventWrite_EventWriteTransfer

- ea: `0x18000af44`
- end: `0x18000af99`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `85`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002036c`

## callees

- `0x18000af44`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000af8e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000af8e`

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

  v5 = (unsigned __int16 *)qword_180037008;
  if ( qword_180037008 )
  {
    UserData->Ptr = qword_180037008;
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
  return EventWriteTransfer(Microsoft_Windows_RadioManager_Context, a2, 0, 0, 1u, UserData);
}

```

## disassembly

```asm
0x18000af44  sub     rsp, 38h
0x18000af48  mov     rcx, cs:qword_180037008
0x18000af4f  mov     rax, [rsp+38h+arg_20]
0x18000af54  test    rcx, rcx
0x18000af57  jnz     short loc_18000AF61
0x18000af59  mov     [rax], rcx
0x18000af5c  xor     r8d, r8d
0x18000af5f  jmp     short loc_18000AF6D
0x18000af61  mov     [rax], rcx
0x18000af64  mov     r8d, 2
0x18000af6a  movzx   ecx, word ptr [rcx]
0x18000af6d  mov     [rax+8], ecx
0x18000af70  xor     r9d, r9d; RelatedActivityId
0x18000af73  mov     [rax+0Ch], r8d
0x18000af77  xor     r8d, r8d; ActivityId
0x18000af7a  mov     rcx, cs:Microsoft_Windows_RadioManager_Context; RegHandle
0x18000af81  mov     [rsp+38h+UserData], rax; UserData
0x18000af86  mov     [rsp+38h+UserDataCount], 1; UserDataCount
0x18000af8e  call    cs:__imp_EventWriteTransfer
0x18000af94  add     rsp, 38h
0x18000af98  retn
```
