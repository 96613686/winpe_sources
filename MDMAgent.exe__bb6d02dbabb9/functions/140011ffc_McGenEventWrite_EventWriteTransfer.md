# McGenEventWrite_EventWriteTransfer

- ea: `0x140011ffc`
- end: `0x140012050`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `84`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x14000f9a4`
- `0x140012058`
- `0x1400120b8`
- `0x14001218c`
- `0x140012210`
- `0x1400122b4`
- `0x14001235c`

## callees

- `0x140011ffc`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x14001203e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x14001203e`

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
0x140011ffc  sub     rsp, 38h
0x140012000  mov     r8, [rcx+8]
0x140012004  mov     rax, [rsp+38h+arg_20]
0x140012009  test    r8, r8
0x14001200c  jnz     short loc_140012016
0x14001200e  mov     [rax], r8
0x140012011  xor     r10d, r10d
0x140012014  jmp     short loc_140012023
0x140012016  mov     [rax], r8
0x140012019  mov     r10d, 2
0x14001201f  movzx   r8d, word ptr [r8]
0x140012023  mov     [rax+8], r8d
0x140012027  xor     r8d, r8d; ActivityId
0x14001202a  mov     [rsp+38h+UserData], rax; UserData
0x14001202f  mov     [rax+0Ch], r10d
0x140012033  mov     rcx, [rcx]; RegHandle
0x140012036  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x14001203b  xor     r9d, r9d; RelatedActivityId
0x14001203e  call    cs:__imp_EventWriteTransfer
0x140012045  nop     dword ptr [rax+rax+00h]
0x14001204a  add     rsp, 38h
0x14001204e  retn
```
