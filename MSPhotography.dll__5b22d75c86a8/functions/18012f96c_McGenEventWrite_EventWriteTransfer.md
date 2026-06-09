# McGenEventWrite_EventWriteTransfer

- ea: `0x18012f96c`
- end: `0x18012f9c5`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `89`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18012f9cc`

## callees

- `0x18012f96c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18012f9ba`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18012f9ba`

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

  v5 = (unsigned __int16 *)qword_18015F058;
  if ( qword_18015F058 )
  {
    UserData->Ptr = qword_18015F058;
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
           Microsoft_Windows_MediaFoundation_Platform_Context,
           &Platform_TraceFailure,
           0,
           0,
           5u,
           UserData);
}

```

## disassembly

```asm
0x18012f96c  sub     rsp, 38h
0x18012f970  mov     rcx, cs:qword_18015F058
0x18012f977  mov     rax, [rsp+38h+arg_20]
0x18012f97c  test    rcx, rcx
0x18012f97f  jnz     short loc_18012F988
0x18012f981  mov     [rax], rcx
0x18012f984  xor     edx, edx
0x18012f986  jmp     short loc_18012F993
0x18012f988  mov     [rax], rcx
0x18012f98b  mov     edx, 2
0x18012f990  movzx   ecx, word ptr [rcx]
0x18012f993  mov     [rax+8], ecx
0x18012f996  xor     r9d, r9d; RelatedActivityId
0x18012f999  mov     [rax+0Ch], edx
0x18012f99c  xor     r8d, r8d; ActivityId
0x18012f99f  mov     rcx, cs:Microsoft_Windows_MediaFoundation_Platform_Context; RegHandle
0x18012f9a6  lea     rdx, Platform_TraceFailure; EventDescriptor
0x18012f9ad  mov     [rsp+38h+UserData], rax; UserData
0x18012f9b2  mov     [rsp+38h+UserDataCount], 5; UserDataCount
0x18012f9ba  call    cs:__imp_EventWriteTransfer
0x18012f9c0  add     rsp, 38h
0x18012f9c4  retn
```
