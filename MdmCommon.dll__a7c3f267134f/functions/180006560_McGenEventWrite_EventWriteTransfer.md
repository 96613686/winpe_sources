# McGenEventWrite_EventWriteTransfer

- ea: `0x180006560`
- end: `0x1800065b9`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `89`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `24`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800030c0`
- `0x1800034c0`
- `0x1800035e0`
- `0x1800036d0`
- `0x180003940`
- `0x180003a30`
- `0x180003fa0`
- `0x1800040d0`
- `0x1800043e0`
- `0x180004550`
- `0x180004a10`
- `0x180004b90`
- `0x180004ca0`
- `0x1800050a0`
- `0x1800053b0`
- `0x1800054a0`
- `0x1800055a0`
- `0x1800056c0`
- `0x1800058b0`
- `0x180005a60`
- `0x180005d00`
- `0x1800065c0`
- `0x18001ad0c`
- `0x18001ceb4`

## callees

- `0x180006560`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800065a7`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800065a7`

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

  v5 = (unsigned __int16 *)qword_180030008;
  if ( qword_180030008 )
  {
    UserData->Ptr = qword_180030008;
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
  return EventWriteTransfer(MICROSOFT_WINDOWS_DEVICEDIRECTORY_MDMCOMMON_ETW_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x180006560  sub     rsp, 38h
0x180006564  mov     rcx, cs:qword_180030008
0x18000656b  mov     rax, [rsp+38h+arg_20]
0x180006570  test    rcx, rcx
0x180006573  jnz     short loc_18000657D
0x180006575  mov     [rax], rcx
0x180006578  xor     r8d, r8d
0x18000657b  jmp     short loc_180006589
0x18000657d  mov     [rax], rcx
0x180006580  mov     r8d, 2
0x180006586  movzx   ecx, word ptr [rcx]
0x180006589  mov     [rax+8], ecx
0x18000658c  mov     [rax+0Ch], r8d
0x180006590  xor     r8d, r8d; ActivityId
0x180006593  mov     rcx, cs:MICROSOFT_WINDOWS_DEVICEDIRECTORY_MDMCOMMON_ETW_Context; RegHandle
0x18000659a  mov     [rsp+38h+UserData], rax; UserData
0x18000659f  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x1800065a4  xor     r9d, r9d; RelatedActivityId
0x1800065a7  call    cs:__imp_EventWriteTransfer
0x1800065ae  nop     dword ptr [rax+rax+00h]
0x1800065b3  add     rsp, 38h
0x1800065b7  retn
```
