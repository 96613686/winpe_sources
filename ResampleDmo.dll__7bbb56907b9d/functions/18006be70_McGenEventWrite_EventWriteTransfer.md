# McGenEventWrite_EventWriteTransfer

- ea: `0x18006be70`
- end: `0x18006bec2`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18006bec8`
- `0x18006bf54`
- `0x18006bfcc`
- `0x180080ef0`
- `0x1800810b0`
- `0x180081ec0`

## callees

- `0x18006be70`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18006beb7`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18006beb7`

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

  v5 = (unsigned __int16 *)qword_1800B39B8;
  if ( qword_1800B39B8 )
  {
    UserData->Ptr = qword_1800B39B8;
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
  return EventWriteTransfer(Microsoft_Windows_MediaFoundation_Performance_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x18006be70  sub     rsp, 38h
0x18006be74  mov     rcx, cs:qword_1800B39B8
0x18006be7b  mov     rax, [rsp+38h+arg_20]
0x18006be80  test    rcx, rcx
0x18006be83  jnz     short loc_18006BE8D
0x18006be85  mov     [rax], rcx
0x18006be88  xor     r8d, r8d
0x18006be8b  jmp     short loc_18006BE99
0x18006be8d  mov     [rax], rcx
0x18006be90  mov     r8d, 2
0x18006be96  movzx   ecx, word ptr [rcx]
0x18006be99  mov     [rax+8], ecx
0x18006be9c  mov     [rax+0Ch], r8d
0x18006bea0  xor     r8d, r8d; ActivityId
0x18006bea3  mov     rcx, cs:Microsoft_Windows_MediaFoundation_Performance_Context; RegHandle
0x18006beaa  mov     [rsp+38h+UserData], rax; UserData
0x18006beaf  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18006beb4  xor     r9d, r9d; RelatedActivityId
0x18006beb7  call    cs:__imp_EventWriteTransfer
0x18006bebd  add     rsp, 38h
0x18006bec1  retn
```
