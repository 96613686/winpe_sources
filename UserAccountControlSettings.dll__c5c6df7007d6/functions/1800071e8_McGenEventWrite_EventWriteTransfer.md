# McGenEventWrite_EventWriteTransfer

- ea: `0x1800071e8`
- end: `0x180007241`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `89`
- prototype: `ULONG __fastcall(__int64, __int64, __int64, __int64, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180005d88`

## callees

- `0x1800071e8`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180007236`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180007236`

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

  v5 = (unsigned __int16 *)qword_180015008;
  if ( qword_180015008 )
  {
    UserData->Ptr = qword_180015008;
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
  return EventWriteTransfer(
           Microsoft_Windows_UserAccountControl_Context,
           &UserAccountControl_UIReady_Stop,
           0,
           0,
           1u,
           UserData);
}

```

## disassembly

```asm
0x1800071e8  sub     rsp, 38h
0x1800071ec  mov     rcx, cs:qword_180015008
0x1800071f3  mov     rax, [rsp+38h+arg_20]
0x1800071f8  test    rcx, rcx
0x1800071fb  jnz     short loc_180007204
0x1800071fd  mov     [rax], rcx
0x180007200  xor     edx, edx
0x180007202  jmp     short loc_18000720F
0x180007204  mov     [rax], rcx
0x180007207  mov     edx, 2
0x18000720c  movzx   ecx, word ptr [rcx]
0x18000720f  mov     [rax+8], ecx
0x180007212  xor     r9d, r9d; RelatedActivityId
0x180007215  mov     [rax+0Ch], edx
0x180007218  xor     r8d, r8d; ActivityId
0x18000721b  mov     rcx, cs:Microsoft_Windows_UserAccountControl_Context; RegHandle
0x180007222  lea     rdx, UserAccountControl_UIReady_Stop; EventDescriptor
0x180007229  mov     [rsp+38h+UserData], rax; UserData
0x18000722e  mov     [rsp+38h+UserDataCount], 1; UserDataCount
0x180007236  call    cs:__imp_EventWriteTransfer
0x18000723c  add     rsp, 38h
0x180007240  retn
```
