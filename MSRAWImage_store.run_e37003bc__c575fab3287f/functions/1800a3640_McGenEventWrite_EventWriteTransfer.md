# McGenEventWrite_EventWriteTransfer

- ea: `0x1800a3640`
- end: `0x1800a36a2`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `98`
- prototype: `__int64 __fastcall(int, int, int, int, PEVENT_DATA_DESCRIPTOR)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800a36a8`

## callees

- `0x1800a3640`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800a3690`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800a3690`

## pseudocode

```c
ULONG __fastcall McGenEventWrite_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // rdx
  ULONG v6; // eax
  ULONG v7; // edx

  v5 = (unsigned __int16 *)qword_1800E5138;
  v6 = 0;
  if ( qword_1800E5138 )
  {
    UserData->Ptr = qword_1800E5138;
    v6 = 2;
    v7 = *v5;
  }
  else
  {
    UserData->Ptr = 0;
    v7 = 0;
  }
  UserData->Size = v7;
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
0x1800a3640  sub     rsp, 38h
0x1800a3644  mov     rdx, cs:qword_1800E5138
0x1800a364b  xor     eax, eax
0x1800a364d  mov     rcx, [rsp+38h+arg_20]
0x1800a3652  test    rdx, rdx
0x1800a3655  jnz     short loc_1800A365E
0x1800a3657  mov     [rcx], rax
0x1800a365a  mov     edx, eax
0x1800a365c  jmp     short loc_1800A3669
0x1800a365e  mov     [rcx], rdx
0x1800a3661  mov     eax, 2
0x1800a3666  movzx   edx, word ptr [rdx]
0x1800a3669  mov     [rcx+8], edx
0x1800a366c  xor     r9d, r9d; RelatedActivityId
0x1800a366f  mov     [rsp+38h+UserData], rcx; UserData
0x1800a3674  lea     rdx, Platform_TraceFailure; EventDescriptor
0x1800a367b  mov     [rcx+0Ch], eax
0x1800a367e  xor     r8d, r8d; ActivityId
0x1800a3681  mov     rcx, cs:Microsoft_Windows_MediaFoundation_Platform_Context; RegHandle
0x1800a3688  mov     [rsp+38h+UserDataCount], 5; UserDataCount
0x1800a3690  call    cs:__imp_EventWriteTransfer
0x1800a3697  nop     dword ptr [rax+rax+00h]
0x1800a369c  add     rsp, 38h
0x1800a36a0  retn
```
