# McGenEventWrite_EventWriteTransfer

- ea: `0x18000e0e4`
- end: `0x18000e136`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: ``
- caller_count: `12`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000de6c`
- `0x18000f268`
- `0x18000f33c`
- `0x18000fb58`
- `0x18000fcc4`
- `0x18000fda8`
- `0x18000fe44`
- `0x18000ff00`
- `0x180010018`
- `0x180010280`
- `0x18001043c`
- `0x180030758`

## callees

- `0x18000e0e4`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000e12b`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000e12b`

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

  v5 = (unsigned __int16 *)qword_18004D738;
  if ( qword_18004D738 )
  {
    UserData->Ptr = qword_18004D738;
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
  return EventWriteTransfer(Microsoft_Windows_SMBWitnessClient_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x18000e0e4  sub     rsp, 38h
0x18000e0e8  mov     rcx, cs:qword_18004D738
0x18000e0ef  mov     rax, [rsp+38h+arg_20]
0x18000e0f4  test    rcx, rcx
0x18000e0f7  jnz     short loc_18000E101
0x18000e0f9  mov     [rax], rcx
0x18000e0fc  xor     r8d, r8d
0x18000e0ff  jmp     short loc_18000E10D
0x18000e101  mov     [rax], rcx
0x18000e104  mov     r8d, 2
0x18000e10a  movzx   ecx, word ptr [rcx]
0x18000e10d  mov     [rax+8], ecx
0x18000e110  mov     [rax+0Ch], r8d
0x18000e114  xor     r8d, r8d; ActivityId
0x18000e117  mov     rcx, cs:Microsoft_Windows_SMBWitnessClient_Context; RegHandle
0x18000e11e  mov     [rsp+38h+UserData], rax; UserData
0x18000e123  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18000e128  xor     r9d, r9d; RelatedActivityId
0x18000e12b  call    cs:__imp_EventWriteTransfer
0x18000e131  add     rsp, 38h
0x18000e135  retn
```
