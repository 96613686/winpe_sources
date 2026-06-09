# McGenEventWrite_EventWriteTransfer

- ea: `0x1800064f0`
- end: `0x180006542`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `24`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800030c0`
- `0x1800034b0`
- `0x1800035d0`
- `0x1800036c0`
- `0x180003930`
- `0x180003a20`
- `0x180003f90`
- `0x1800040c0`
- `0x1800043b0`
- `0x180004520`
- `0x1800049e0`
- `0x180004b60`
- `0x180004c70`
- `0x180005070`
- `0x180005360`
- `0x180005450`
- `0x180005550`
- `0x180005670`
- `0x180005860`
- `0x180005a10`
- `0x180005cb0`
- `0x180006548`
- `0x18001a7c0`
- `0x18001c850`

## callees

- `0x1800064f0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180006537`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180006537`

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
0x1800064f0  sub     rsp, 38h
0x1800064f4  mov     rcx, cs:qword_180030008
0x1800064fb  mov     rax, [rsp+38h+arg_20]
0x180006500  test    rcx, rcx
0x180006503  jnz     short loc_18000650D
0x180006505  mov     [rax], rcx
0x180006508  xor     r8d, r8d
0x18000650b  jmp     short loc_180006519
0x18000650d  mov     [rax], rcx
0x180006510  mov     r8d, 2
0x180006516  movzx   ecx, word ptr [rcx]
0x180006519  mov     [rax+8], ecx
0x18000651c  mov     [rax+0Ch], r8d
0x180006520  xor     r8d, r8d; ActivityId
0x180006523  mov     rcx, cs:MICROSOFT_WINDOWS_DEVICEDIRECTORY_MDMCOMMON_ETW_Context; RegHandle
0x18000652a  mov     [rsp+38h+UserData], rax; UserData
0x18000652f  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x180006534  xor     r9d, r9d; RelatedActivityId
0x180006537  call    cs:__imp_EventWriteTransfer
0x18000653d  add     rsp, 38h
0x180006541  retn
```
