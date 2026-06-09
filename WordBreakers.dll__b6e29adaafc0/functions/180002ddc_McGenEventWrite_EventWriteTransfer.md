# McGenEventWrite_EventWriteTransfer

- ea: `0x180002ddc`
- end: `0x180002e35`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `89`
- prototype: `ULONG __fastcall(__int64, __int64, __int64, __int64, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002e3c`

## callees

- `0x180002ddc`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180002e2a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180002e2a`

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

  v5 = (unsigned __int16 *)qword_180012008;
  if ( qword_180012008 )
  {
    UserData->Ptr = qword_180012008;
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
0x180002ddc  sub     rsp, 38h
0x180002de0  mov     rcx, cs:qword_180012008
0x180002de7  mov     rax, [rsp+38h+arg_20]
0x180002dec  test    rcx, rcx
0x180002def  jnz     short loc_180002DF8
0x180002df1  mov     [rax], rcx
0x180002df4  xor     edx, edx
0x180002df6  jmp     short loc_180002E03
0x180002df8  mov     [rax], rcx
0x180002dfb  mov     edx, 2
0x180002e00  movzx   ecx, word ptr [rcx]
0x180002e03  mov     [rax+8], ecx
0x180002e06  xor     r9d, r9d; RelatedActivityId
0x180002e09  mov     [rax+0Ch], edx
0x180002e0c  xor     r8d, r8d; ActivityId
0x180002e0f  mov     rcx, cs:MICROSOFT_WINDOWSPHONE_INPUT_Context; RegHandle
0x180002e16  lea     rdx, _EhmMessage; EventDescriptor
0x180002e1d  mov     [rsp+38h+UserData], rax; UserData
0x180002e22  mov     [rsp+38h+UserDataCount], 4; UserDataCount
0x180002e2a  call    cs:__imp_EventWriteTransfer
0x180002e30  add     rsp, 38h
0x180002e34  retn
```
