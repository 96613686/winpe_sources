# McGenEventWrite_EventWriteTransfer

- ea: `0x18001d6f8`
- end: `0x18001d74d`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `85`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001d754`

## callees

- `0x18001d6f8`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001d742`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001d742`

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

  v5 = (unsigned __int16 *)qword_18002F008;
  if ( qword_18002F008 )
  {
    UserData->Ptr = qword_18002F008;
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
  return EventWriteTransfer(Microsoft_Windows_Graphics_Capture_Server_Provider_Context, a2, 0, 0, 2u, UserData);
}

```

## disassembly

```asm
0x18001d6f8  sub     rsp, 38h
0x18001d6fc  mov     rcx, cs:qword_18002F008
0x18001d703  mov     r9d, 2
0x18001d709  mov     rax, [rsp+38h+arg_20]
0x18001d70e  test    rcx, rcx
0x18001d711  jnz     short loc_18001D71B
0x18001d713  mov     [rax], rcx
0x18001d716  xor     r8d, r8d
0x18001d719  jmp     short loc_18001D724
0x18001d71b  mov     [rax], rcx
0x18001d71e  mov     r8d, r9d
0x18001d721  movzx   ecx, word ptr [rcx]
0x18001d724  mov     [rax+8], ecx
0x18001d727  mov     [rax+0Ch], r8d
0x18001d72b  xor     r8d, r8d; ActivityId
0x18001d72e  mov     rcx, cs:Microsoft_Windows_Graphics_Capture_Server_Provider_Context; RegHandle
0x18001d735  mov     [rsp+38h+UserData], rax; UserData
0x18001d73a  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18001d73f  xor     r9d, r9d; RelatedActivityId
0x18001d742  call    cs:__imp_EventWriteTransfer
0x18001d748  add     rsp, 38h
0x18001d74c  retn
```
