# McGenEventWrite_EventWriteTransfer

- ea: `0x18000d384`
- end: `0x18000d3dd`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `89`
- prototype: `ULONG __fastcall(__int64, __int64, __int64, __int64, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000d300`

## callees

- `0x18000d384`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000d3d2`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000d3d2`

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

  v5 = (unsigned __int16 *)qword_180017148;
  if ( qword_180017148 )
  {
    UserData->Ptr = qword_180017148;
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
  return EventWriteTransfer(MICROSOFT_WINDOWS_DEVICESETUPMANAGER_Context, &DriverRecoveryRequested, 0, 0, 1u, UserData);
}

```

## disassembly

```asm
0x18000d384  sub     rsp, 38h
0x18000d388  mov     rcx, cs:qword_180017148
0x18000d38f  mov     rax, [rsp+38h+arg_20]
0x18000d394  test    rcx, rcx
0x18000d397  jnz     short loc_18000D3A0
0x18000d399  mov     [rax], rcx
0x18000d39c  xor     edx, edx
0x18000d39e  jmp     short loc_18000D3AB
0x18000d3a0  mov     [rax], rcx
0x18000d3a3  mov     edx, 2
0x18000d3a8  movzx   ecx, word ptr [rcx]
0x18000d3ab  mov     [rax+8], ecx
0x18000d3ae  xor     r9d, r9d; RelatedActivityId
0x18000d3b1  mov     [rax+0Ch], edx
0x18000d3b4  xor     r8d, r8d; ActivityId
0x18000d3b7  mov     rcx, cs:MICROSOFT_WINDOWS_DEVICESETUPMANAGER_Context; RegHandle
0x18000d3be  lea     rdx, DriverRecoveryRequested; EventDescriptor
0x18000d3c5  mov     [rsp+38h+UserData], rax; UserData
0x18000d3ca  mov     [rsp+38h+UserDataCount], 1; UserDataCount
0x18000d3d2  call    cs:__imp_EventWriteTransfer
0x18000d3d8  add     rsp, 38h
0x18000d3dc  retn
```
