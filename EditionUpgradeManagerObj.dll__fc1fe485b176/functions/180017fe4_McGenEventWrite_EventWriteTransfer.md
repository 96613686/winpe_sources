# McGenEventWrite_EventWriteTransfer

- ea: `0x180017fe4`
- end: `0x18001803e`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `90`
- prototype: `ULONG __fastcall(__int64, __int64, __int64, __int64, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180017ef8`

## callees

- `0x180017fe4`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180018033`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180018033`

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

  v5 = (unsigned __int16 *)qword_18002F178;
  if ( qword_18002F178 )
  {
    UserData->Ptr = qword_18002F178;
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
           Microsoft_Windows_Security_SPP_UX_GenuineCenter_Context,
           &Security_SPP_UX_GC_LogError,
           0,
           0,
           2u,
           UserData);
}

```

## disassembly

```asm
0x180017fe4  sub     rsp, 38h
0x180017fe8  mov     rcx, cs:qword_18002F178
0x180017fef  mov     r8d, 2
0x180017ff5  mov     rax, [rsp+38h+arg_20]
0x180017ffa  test    rcx, rcx
0x180017ffd  jnz     short loc_180018006
0x180017fff  mov     [rax], rcx
0x180018002  xor     edx, edx
0x180018004  jmp     short loc_18001800F
0x180018006  mov     [rax], rcx
0x180018009  mov     edx, r8d
0x18001800c  movzx   ecx, word ptr [rcx]
0x18001800f  mov     [rax+8], ecx
0x180018012  xor     r9d, r9d; RelatedActivityId
0x180018015  mov     [rax+0Ch], edx
0x180018018  lea     rdx, Security_SPP_UX_GC_LogError; EventDescriptor
0x18001801f  mov     rcx, cs:Microsoft_Windows_Security_SPP_UX_GenuineCenter_Context; RegHandle
0x180018026  mov     [rsp+38h+UserData], rax; UserData
0x18001802b  mov     [rsp+38h+UserDataCount], r8d; UserDataCount
0x180018030  xor     r8d, r8d; ActivityId
0x180018033  call    cs:__imp_EventWriteTransfer
0x180018039  add     rsp, 38h
0x18001803d  retn
```
