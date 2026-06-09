# McGenEventWrite_EventWriteTransfer

- ea: `0x18002aedc`
- end: `0x18002af35`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `89`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002af3c`

## callees

- `0x18002aedc`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002af2a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002af2a`

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

  v5 = (unsigned __int16 *)qword_18004A008;
  if ( qword_18004A008 )
  {
    UserData->Ptr = qword_18004A008;
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
  return EventWriteTransfer(WPNCORE_PROVIDER_GUID_Context, &WPNCORE_EVENT_DEBUG, 0, 0, 6u, UserData);
}

```

## disassembly

```asm
0x18002aedc  sub     rsp, 38h
0x18002aee0  mov     rcx, cs:qword_18004A008
0x18002aee7  mov     rax, [rsp+38h+arg_20]
0x18002aeec  test    rcx, rcx
0x18002aeef  jnz     short loc_18002AEF8
0x18002aef1  mov     [rax], rcx
0x18002aef4  xor     edx, edx
0x18002aef6  jmp     short loc_18002AF03
0x18002aef8  mov     [rax], rcx
0x18002aefb  mov     edx, 2
0x18002af00  movzx   ecx, word ptr [rcx]
0x18002af03  mov     [rax+8], ecx
0x18002af06  xor     r9d, r9d; RelatedActivityId
0x18002af09  mov     [rax+0Ch], edx
0x18002af0c  xor     r8d, r8d; ActivityId
0x18002af0f  mov     rcx, cs:WPNCORE_PROVIDER_GUID_Context; RegHandle
0x18002af16  lea     rdx, WPNCORE_EVENT_DEBUG; EventDescriptor
0x18002af1d  mov     [rsp+38h+UserData], rax; UserData
0x18002af22  mov     [rsp+38h+UserDataCount], 6; UserDataCount
0x18002af2a  call    cs:__imp_EventWriteTransfer
0x18002af30  add     rsp, 38h
0x18002af34  retn
```
