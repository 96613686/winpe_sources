# McGenEventWrite_EventWriteTransfer

- ea: `0x180005060`
- end: `0x1800050b2`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `14`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180004640`
- `0x1800050b8`
- `0x180005190`
- `0x180005b34`
- `0x180005f5c`
- `0x1800063f4`
- `0x180006c00`
- `0x180006da4`
- `0x1800071d0`
- `0x180007838`
- `0x18000c034`
- `0x18000ed24`
- `0x18000f23c`
- `0x18000f35c`

## callees

- `0x180005060`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800050a7`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800050a7`

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

  v5 = (unsigned __int16 *)qword_180049008;
  if ( qword_180049008 )
  {
    UserData->Ptr = qword_180049008;
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
           MICROSOFT_WINDOWS_DEVICE_DIRECTORY_DEVICE_DIRECTORY_CLIENT_ETW_Context,
           a2,
           0,
           0,
           UserDataCount,
           UserData);
}

```

## disassembly

```asm
0x180005060  sub     rsp, 38h
0x180005064  mov     rcx, cs:qword_180049008
0x18000506b  mov     rax, [rsp+38h+arg_20]
0x180005070  test    rcx, rcx
0x180005073  jnz     short loc_18000507D
0x180005075  mov     [rax], rcx
0x180005078  xor     r8d, r8d
0x18000507b  jmp     short loc_180005089
0x18000507d  mov     [rax], rcx
0x180005080  mov     r8d, 2
0x180005086  movzx   ecx, word ptr [rcx]
0x180005089  mov     [rax+8], ecx
0x18000508c  mov     [rax+0Ch], r8d
0x180005090  xor     r8d, r8d; ActivityId
0x180005093  mov     rcx, cs:MICROSOFT_WINDOWS_DEVICE_DIRECTORY_DEVICE_DIRECTORY_CLIENT_ETW_Context; RegHandle
0x18000509a  mov     [rsp+38h+UserData], rax; UserData
0x18000509f  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x1800050a4  xor     r9d, r9d; RelatedActivityId
0x1800050a7  call    cs:__imp_EventWriteTransfer
0x1800050ad  add     rsp, 38h
0x1800050b1  retn
```
