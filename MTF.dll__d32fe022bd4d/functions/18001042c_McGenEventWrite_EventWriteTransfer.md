# McGenEventWrite_EventWriteTransfer

- ea: `0x18001042c`
- end: `0x180010485`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `89`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001048c`

## callees

- `0x18001042c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001047a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001047a`

## pseudocode

```c
ULONG __fastcall McGenEventWrite_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // rcx
  ULONG v6; // edx

  v5 = (unsigned __int16 *)qword_18003E008;
  if ( qword_18003E008 )
  {
    UserData->Ptr = qword_18003E008;
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
  return EventWriteTransfer(MICROSOFT_WINDOWSPHONE_INPUT_Context, &EhmMessage, 0, 0, 4u, UserData);
}

```

## disassembly

```asm
0x18001042c  sub     rsp, 38h
0x180010430  mov     rcx, cs:qword_18003E008
0x180010437  mov     rax, [rsp+38h+arg_20]
0x18001043c  test    rcx, rcx
0x18001043f  jnz     short loc_180010448
0x180010441  mov     [rax], rcx
0x180010444  xor     edx, edx
0x180010446  jmp     short loc_180010453
0x180010448  mov     [rax], rcx
0x18001044b  mov     edx, 2
0x180010450  movzx   ecx, word ptr [rcx]
0x180010453  mov     [rax+8], ecx
0x180010456  xor     r9d, r9d; RelatedActivityId
0x180010459  mov     [rax+0Ch], edx
0x18001045c  xor     r8d, r8d; ActivityId
0x18001045f  mov     rcx, cs:MICROSOFT_WINDOWSPHONE_INPUT_Context; RegHandle
0x180010466  lea     rdx, _EhmMessage; EventDescriptor
0x18001046d  mov     [rsp+38h+UserData], rax; UserData
0x180010472  mov     [rsp+38h+UserDataCount], 4; UserDataCount
0x18001047a  call    cs:__imp_EventWriteTransfer
0x180010480  add     rsp, 38h
0x180010484  retn
```
