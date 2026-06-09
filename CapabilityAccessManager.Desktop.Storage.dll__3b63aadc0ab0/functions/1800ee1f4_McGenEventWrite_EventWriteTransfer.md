# McGenEventWrite_EventWriteTransfer

- ea: `0x1800ee1f4`
- end: `0x1800ee246`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800ee24c`
- `0x1800f2a54`
- `0x1800f4a04`
- `0x1800f4a70`

## callees

- `0x1800ee1f4`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800ee23b`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800ee23b`

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

  v5 = (unsigned __int16 *)qword_18013F548;
  if ( qword_18013F548 )
  {
    UserData->Ptr = qword_18013F548;
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
  return EventWriteTransfer(MICROSOFT_WINDOWS_PRIVACY_AUDITING_PROVIDER_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x1800ee1f4  sub     rsp, 38h
0x1800ee1f8  mov     rcx, cs:qword_18013F548
0x1800ee1ff  mov     rax, [rsp+38h+arg_20]
0x1800ee204  test    rcx, rcx
0x1800ee207  jnz     short loc_1800EE211
0x1800ee209  mov     [rax], rcx
0x1800ee20c  xor     r8d, r8d
0x1800ee20f  jmp     short loc_1800EE21D
0x1800ee211  mov     [rax], rcx
0x1800ee214  mov     r8d, 2
0x1800ee21a  movzx   ecx, word ptr [rcx]
0x1800ee21d  mov     [rax+8], ecx
0x1800ee220  mov     [rax+0Ch], r8d
0x1800ee224  xor     r8d, r8d; ActivityId
0x1800ee227  mov     rcx, cs:MICROSOFT_WINDOWS_PRIVACY_AUDITING_PROVIDER_Context; RegHandle
0x1800ee22e  mov     [rsp+38h+UserData], rax; UserData
0x1800ee233  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x1800ee238  xor     r9d, r9d; RelatedActivityId
0x1800ee23b  call    cs:__imp_EventWriteTransfer
0x1800ee241  add     rsp, 38h
0x1800ee245  retn
```
