# McGenEventWrite_EventWriteTransfer

- ea: `0x18001b64c`
- end: `0x18001b6a1`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `85`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `24`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180018680`
- `0x1800195f0`
- `0x180019900`
- `0x180019c70`
- `0x18001a3f0`
- `0x18001cb40`
- `0x18001d210`
- `0x18001d480`
- `0x18001dd60`
- `0x18001e510`
- `0x180023e1c`
- `0x1800264a0`
- `0x180026800`
- `0x1800276f0`
- `0x180027fb0`
- `0x18002b770`
- `0x18002e9f0`
- `0x180030750`
- `0x180033f60`
- `0x180034730`
- `0x180034ea0`
- `0x18003b6d0`
- `0x18003be60`
- `0x180051600`

## callees

- `0x18001b64c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001b696`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001b696`

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

  v5 = (unsigned __int16 *)qword_18015B008;
  if ( qword_18015B008 )
  {
    UserData->Ptr = qword_18015B008;
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
  return EventWriteTransfer(Microsoft_Windows_UI_Input_Inking_Context, a2, 0, 0, 1u, UserData);
}

```

## disassembly

```asm
0x18001b64c  sub     rsp, 38h
0x18001b650  mov     rcx, cs:qword_18015B008
0x18001b657  mov     rax, [rsp+38h+arg_20]
0x18001b65c  test    rcx, rcx
0x18001b65f  jnz     short loc_18001B669
0x18001b661  mov     [rax], rcx
0x18001b664  xor     r8d, r8d
0x18001b667  jmp     short loc_18001B675
0x18001b669  mov     [rax], rcx
0x18001b66c  mov     r8d, 2
0x18001b672  movzx   ecx, word ptr [rcx]
0x18001b675  mov     [rax+8], ecx
0x18001b678  xor     r9d, r9d; RelatedActivityId
0x18001b67b  mov     [rax+0Ch], r8d
0x18001b67f  xor     r8d, r8d; ActivityId
0x18001b682  mov     rcx, cs:Microsoft_Windows_UI_Input_Inking_Context; RegHandle
0x18001b689  mov     [rsp+38h+UserData], rax; UserData
0x18001b68e  mov     [rsp+38h+UserDataCount], 1; UserDataCount
0x18001b696  call    cs:__imp_EventWriteTransfer
0x18001b69c  add     rsp, 38h
0x18001b6a0  retn
```
