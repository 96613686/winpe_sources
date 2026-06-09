# McGenEventWrite_EventWriteTransfer

- ea: `0x180028ac8`
- end: `0x180028b22`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `90`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180028b28`

## callees

- `0x180028ac8`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180028b17`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180028b17`

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

  v5 = (unsigned __int16 *)qword_18004B008;
  if ( qword_18004B008 )
  {
    UserData->Ptr = qword_18004B008;
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
  return EventWriteTransfer(S_SCardSvrTrigger_Context, &EVENT_TRIGGER_SCDEVICEENUM, 0, 0, 2u, UserData);
}

```

## disassembly

```asm
0x180028ac8  sub     rsp, 38h
0x180028acc  mov     rcx, cs:qword_18004B008
0x180028ad3  mov     r8d, 2
0x180028ad9  mov     rax, [rsp+38h+arg_20]
0x180028ade  test    rcx, rcx
0x180028ae1  jnz     short loc_180028AEA
0x180028ae3  mov     [rax], rcx
0x180028ae6  xor     edx, edx
0x180028ae8  jmp     short loc_180028AF3
0x180028aea  mov     [rax], rcx
0x180028aed  mov     edx, r8d
0x180028af0  movzx   ecx, word ptr [rcx]
0x180028af3  mov     [rax+8], ecx
0x180028af6  xor     r9d, r9d; RelatedActivityId
0x180028af9  mov     [rax+0Ch], edx
0x180028afc  lea     rdx, EVENT_TRIGGER_SCDEVICEENUM; EventDescriptor
0x180028b03  mov     rcx, cs:S_SCardSvrTrigger_Context; RegHandle
0x180028b0a  mov     [rsp+38h+UserData], rax; UserData
0x180028b0f  mov     [rsp+38h+UserDataCount], r8d; UserDataCount
0x180028b14  xor     r8d, r8d; ActivityId
0x180028b17  call    cs:__imp_EventWriteTransfer
0x180028b1d  add     rsp, 38h
0x180028b21  retn
```
