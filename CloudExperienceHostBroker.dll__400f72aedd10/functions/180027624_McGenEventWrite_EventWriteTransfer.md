# McGenEventWrite_EventWriteTransfer

- ea: `0x180027624`
- end: `0x18002767d`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `89`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180027684`

## callees

- `0x180027624`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180027672`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180027672`

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

  v5 = (unsigned __int16 *)qword_18004E008;
  if ( qword_18004E008 )
  {
    UserData->Ptr = qword_18004E008;
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
  return EventWriteTransfer(
           Microsoft_Windows_Shell_Core_Provider_Context,
           &OOBEHealth_Progress_Info,
           0,
           0,
           7u,
           UserData);
}

```

## disassembly

```asm
0x180027624  sub     rsp, 38h
0x180027628  mov     rcx, cs:qword_18004E008
0x18002762f  mov     rax, [rsp+38h+arg_20]
0x180027634  test    rcx, rcx
0x180027637  jnz     short loc_180027640
0x180027639  mov     [rax], rcx
0x18002763c  xor     edx, edx
0x18002763e  jmp     short loc_18002764B
0x180027640  mov     [rax], rcx
0x180027643  mov     edx, 2
0x180027648  movzx   ecx, word ptr [rcx]
0x18002764b  mov     [rax+8], ecx
0x18002764e  xor     r9d, r9d; RelatedActivityId
0x180027651  mov     [rax+0Ch], edx
0x180027654  xor     r8d, r8d; ActivityId
0x180027657  mov     rcx, cs:Microsoft_Windows_Shell_Core_Provider_Context; RegHandle
0x18002765e  lea     rdx, OOBEHealth_Progress_Info; EventDescriptor
0x180027665  mov     [rsp+38h+UserData], rax; UserData
0x18002766a  mov     [rsp+38h+UserDataCount], 7; UserDataCount
0x180027672  call    cs:__imp_EventWriteTransfer
0x180027678  add     rsp, 38h
0x18002767c  retn
```
