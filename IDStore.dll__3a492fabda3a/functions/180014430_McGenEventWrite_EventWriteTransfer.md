# McGenEventWrite_EventWriteTransfer

- ea: `0x180014430`
- end: `0x180014485`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `85`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, __int64, __int64, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `15`
- callee_count: `1`
- tags: ``

## callers

- `0x180002500`
- `0x180004490`
- `0x180005000`
- `0x180008910`
- `0x18000eb30`
- `0x180012b10`
- `0x180013170`
- `0x1800132b0`
- `0x180013430`
- `0x180013b40`
- `0x180015b30`
- `0x180015d10`
- `0x180016400`
- `0x180017ec0`
- `0x180018040`

## callees

- `0x180014430`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001447a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001447a`

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

  v5 = (unsigned __int16 *)qword_1800260F8;
  if ( qword_1800260F8 )
  {
    UserData->Ptr = qword_1800260F8;
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
  return EventWriteTransfer(MS_IdStore_Provider_Context, a2, 0, 0, 1u, UserData);
}

```

## disassembly

```asm
0x180014430  sub     rsp, 38h
0x180014434  mov     rcx, cs:qword_1800260F8
0x18001443b  mov     rax, [rsp+38h+arg_20]
0x180014440  test    rcx, rcx
0x180014443  jnz     short loc_18001444D
0x180014445  mov     [rax], rcx
0x180014448  xor     r8d, r8d
0x18001444b  jmp     short loc_180014459
0x18001444d  mov     [rax], rcx
0x180014450  mov     r8d, 2
0x180014456  movzx   ecx, word ptr [rcx]
0x180014459  mov     [rax+8], ecx
0x18001445c  xor     r9d, r9d; RelatedActivityId
0x18001445f  mov     [rax+0Ch], r8d
0x180014463  xor     r8d, r8d; ActivityId
0x180014466  mov     rcx, cs:MS_IdStore_Provider_Context; RegHandle
0x18001446d  mov     [rsp+38h+UserData], rax; UserData
0x180014472  mov     [rsp+38h+UserDataCount], 1; UserDataCount
0x18001447a  call    cs:__imp_EventWriteTransfer
0x180014480  add     rsp, 38h
0x180014484  retn
```
