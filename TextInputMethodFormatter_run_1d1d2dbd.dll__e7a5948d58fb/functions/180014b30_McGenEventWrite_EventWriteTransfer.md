# McGenEventWrite_EventWriteTransfer

- ea: `0x180014b30`
- end: `0x180014b89`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `89`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180014b90`

## callees

- `0x180014b30`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180014b7e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180014b7e`

## pseudocode

```c
ULONG __fastcall McGenEventWrite_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // rcx
  ULONG v6; // edx

  v5 = (unsigned __int16 *)qword_180082008;
  if ( qword_180082008 )
  {
    UserData->Ptr = qword_180082008;
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
  return EventWriteTransfer(MICROSOFT_WINDOWSPHONE_INPUT_Context, &EhmMessage, 0, 0, 4u, UserData);
}

```

## disassembly

```asm
0x180014b30  sub     rsp, 38h
0x180014b34  mov     rcx, cs:qword_180082008
0x180014b3b  mov     rax, [rsp+38h+arg_20]
0x180014b40  test    rcx, rcx
0x180014b43  jnz     short loc_180014B4C
0x180014b45  mov     [rax], rcx
0x180014b48  xor     edx, edx
0x180014b4a  jmp     short loc_180014B57
0x180014b4c  mov     [rax], rcx
0x180014b4f  mov     edx, 2
0x180014b54  movzx   ecx, word ptr [rcx]
0x180014b57  mov     [rax+8], ecx
0x180014b5a  xor     r9d, r9d; RelatedActivityId
0x180014b5d  mov     [rax+0Ch], edx
0x180014b60  xor     r8d, r8d; ActivityId
0x180014b63  mov     rcx, cs:MICROSOFT_WINDOWSPHONE_INPUT_Context; RegHandle
0x180014b6a  lea     rdx, _EhmMessage; EventDescriptor
0x180014b71  mov     [rsp+38h+UserData], rax; UserData
0x180014b76  mov     [rsp+38h+UserDataCount], 4; UserDataCount
0x180014b7e  call    cs:__imp_EventWriteTransfer
0x180014b84  add     rsp, 38h
0x180014b88  retn
```
