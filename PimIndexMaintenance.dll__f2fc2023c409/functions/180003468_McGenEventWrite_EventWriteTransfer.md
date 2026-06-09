# McGenEventWrite_EventWriteTransfer

- ea: `0x180003468`
- end: `0x1800034b5`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `77`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `31`
- callee_count: `1`
- tags: ``

## callers

- `0x1800034bc`
- `0x1800042b0`
- `0x180004310`
- `0x180004370`
- `0x1800043d0`
- `0x180004430`
- `0x180004490`
- `0x1800044f0`
- `0x180004550`
- `0x1800045dc`
- `0x1800046a4`
- `0x180004744`
- `0x18000568c`
- `0x1800058d0`
- `0x1800065a8`
- `0x180007630`
- `0x180008060`
- `0x1800082c4`
- `0x1800085a0`
- `0x180008ab0`
- `0x180008da0`
- `0x18000a15c`
- `0x18000ab48`
- `0x18000b004`
- `0x18000c6dc`
- `0x18000c734`
- `0x18000c790`
- `0x18000c800`
- `0x180020e00`
- `0x180020ea4`
- `0x180020f2c`

## callees

- `0x180003468`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800034aa`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800034aa`

## pseudocode

```c
ULONG __fastcall McGenEventWrite_EventWriteTransfer(
        REGHANDLE *a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // r8
  int v6; // r10d

  v5 = (unsigned __int16 *)a1[1];
  if ( v5 )
  {
    UserData->Ptr = (ULONGLONG)v5;
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
  return EventWriteTransfer(*a1, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x180003468  sub     rsp, 38h
0x18000346c  mov     r8, [rcx+8]
0x180003470  mov     rax, [rsp+38h+arg_20]
0x180003475  test    r8, r8
0x180003478  jnz     short loc_180003482
0x18000347a  mov     [rax], r8
0x18000347d  xor     r10d, r10d
0x180003480  jmp     short loc_18000348F
0x180003482  mov     [rax], r8
0x180003485  mov     r10d, 2
0x18000348b  movzx   r8d, word ptr [r8]
0x18000348f  mov     [rax+8], r8d
0x180003493  xor     r8d, r8d; ActivityId
0x180003496  mov     [rsp+38h+UserData], rax; UserData
0x18000349b  mov     [rax+0Ch], r10d
0x18000349f  mov     rcx, [rcx]; RegHandle
0x1800034a2  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x1800034a7  xor     r9d, r9d; RelatedActivityId
0x1800034aa  call    cs:__imp_EventWriteTransfer
0x1800034b0  add     rsp, 38h
0x1800034b4  retn
```
