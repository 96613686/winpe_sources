# McGenEventWrite_EventWriteTransfer

- ea: `0x18001a7fc`
- end: `0x18001a854`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `88`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18001a85c`
- `0x18001a8c0`
- `0x18001b564`
- `0x18001b5d8`
- `0x18001b790`

## callees

- `0x18001a7fc`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001a842`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001a842`

## pseudocode

```c
ULONG __fastcall McGenEventWrite_EventWriteTransfer(
        REGHANDLE *a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        ULONG a4,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // r10
  int v6; // eax
  ULONG v8; // r9d

  v5 = (unsigned __int16 *)a1[1];
  v6 = 0;
  if ( v5 )
  {
    UserData->Ptr = (ULONGLONG)v5;
    v6 = 2;
    v8 = *v5;
  }
  else
  {
    UserData->Ptr = 0;
    v8 = 0;
  }
  UserData->Size = v8;
  UserData->Reserved = v6;
  return EventWriteTransfer(*a1, a2, 0, 0, a4, UserData);
}

```

## disassembly

```asm
0x18001a7fc  sub     rsp, 38h
0x18001a800  mov     r10, [rcx+8]
0x18001a804  xor     eax, eax
0x18001a806  mov     r8, [rsp+38h+arg_20]
0x18001a80b  mov     r11d, r9d
0x18001a80e  test    r10, r10
0x18001a811  jnz     short loc_18001A81B
0x18001a813  mov     [r8], rax
0x18001a816  mov     r9d, eax
0x18001a819  jmp     short loc_18001A827
0x18001a81b  mov     [r8], r10
0x18001a81e  mov     eax, 2
0x18001a823  movzx   r9d, word ptr [r10]
0x18001a827  mov     [r8+8], r9d
0x18001a82b  xor     r9d, r9d; RelatedActivityId
0x18001a82e  mov     [r8+0Ch], eax
0x18001a832  mov     rcx, [rcx]; RegHandle
0x18001a835  mov     [rsp+38h+UserData], r8; UserData
0x18001a83a  xor     r8d, r8d; ActivityId
0x18001a83d  mov     [rsp+38h+UserDataCount], r11d; UserDataCount
0x18001a842  call    cs:__imp_EventWriteTransfer
0x18001a849  nop     dword ptr [rax+rax+00h]
0x18001a84e  add     rsp, 38h
0x18001a852  retn
```
