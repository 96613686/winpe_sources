# McGenEventWrite_EventWriteTransfer

- ea: `0x18002f9fc`
- end: `0x18002fa56`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `90`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002c830`

## callees

- `0x18002f9fc`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002fa4b`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002fa4b`

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

  v5 = (unsigned __int16 *)qword_180044018;
  if ( qword_180044018 )
  {
    UserData->Ptr = qword_180044018;
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
  return EventWriteTransfer(BTHLEPREPAIRING_EVENT_PROVIDER_Context, &BthLEPrepairing_Complete, 0, 0, 2u, UserData);
}

```

## disassembly

```asm
0x18002f9fc  sub     rsp, 38h
0x18002fa00  mov     rcx, cs:qword_180044018
0x18002fa07  mov     r8d, 2
0x18002fa0d  mov     rax, [rsp+38h+arg_20]
0x18002fa12  test    rcx, rcx
0x18002fa15  jnz     short loc_18002FA1E
0x18002fa17  mov     [rax], rcx
0x18002fa1a  xor     edx, edx
0x18002fa1c  jmp     short loc_18002FA27
0x18002fa1e  mov     [rax], rcx
0x18002fa21  mov     edx, r8d
0x18002fa24  movzx   ecx, word ptr [rcx]
0x18002fa27  mov     [rax+8], ecx
0x18002fa2a  xor     r9d, r9d; RelatedActivityId
0x18002fa2d  mov     [rax+0Ch], edx
0x18002fa30  lea     rdx, BthLEPrepairing_Complete; EventDescriptor
0x18002fa37  mov     rcx, cs:BTHLEPREPAIRING_EVENT_PROVIDER_Context; RegHandle
0x18002fa3e  mov     [rsp+38h+UserData], rax; UserData
0x18002fa43  mov     [rsp+38h+UserDataCount], r8d; UserDataCount
0x18002fa48  xor     r8d, r8d; ActivityId
0x18002fa4b  call    cs:__imp_EventWriteTransfer
0x18002fa51  add     rsp, 38h
0x18002fa55  retn
```
