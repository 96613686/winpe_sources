# McGenEventWrite_EventWriteTransfer

- ea: `0x140009f90`
- end: `0x140009fe5`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `85`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140009fec`

## callees

- `0x140009f90`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140009fda`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140009fda`

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

  v5 = (unsigned __int16 *)qword_140030078;
  if ( qword_140030078 )
  {
    UserData->Ptr = qword_140030078;
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
  return EventWriteTransfer(PUBLISHER_WINDOWSPHONE_SPEECH_Context, a2, 0, 0, 2u, UserData);
}

```

## disassembly

```asm
0x140009f90  sub     rsp, 38h
0x140009f94  mov     rcx, cs:qword_140030078
0x140009f9b  mov     r9d, 2
0x140009fa1  mov     rax, [rsp+38h+arg_20]
0x140009fa6  test    rcx, rcx
0x140009fa9  jnz     short loc_140009FB3
0x140009fab  mov     [rax], rcx
0x140009fae  xor     r8d, r8d
0x140009fb1  jmp     short loc_140009FBC
0x140009fb3  mov     [rax], rcx
0x140009fb6  mov     r8d, r9d
0x140009fb9  movzx   ecx, word ptr [rcx]
0x140009fbc  mov     [rax+8], ecx
0x140009fbf  mov     [rax+0Ch], r8d
0x140009fc3  xor     r8d, r8d; ActivityId
0x140009fc6  mov     rcx, cs:PUBLISHER_WINDOWSPHONE_SPEECH_Context; RegHandle
0x140009fcd  mov     [rsp+38h+UserData], rax; UserData
0x140009fd2  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x140009fd7  xor     r9d, r9d; RelatedActivityId
0x140009fda  call    cs:__imp_EventWriteTransfer
0x140009fe0  add     rsp, 38h
0x140009fe4  retn
```
