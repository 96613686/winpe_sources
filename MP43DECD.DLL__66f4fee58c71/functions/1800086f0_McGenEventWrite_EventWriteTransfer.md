# McGenEventWrite_EventWriteTransfer

- ea: `0x1800086f0`
- end: `0x180008742`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800022e4`
- `0x180002634`
- `0x180008748`

## callees

- `0x1800086f0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180008737`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180008737`

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

  v5 = (unsigned __int16 *)qword_180027078;
  if ( qword_180027078 )
  {
    UserData->Ptr = qword_180027078;
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
  return EventWriteTransfer(Microsoft_Windows_MediaFoundation_Performance_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x1800086f0  sub     rsp, 38h
0x1800086f4  mov     rcx, cs:qword_180027078
0x1800086fb  mov     rax, [rsp+38h+arg_20]
0x180008700  test    rcx, rcx
0x180008703  jnz     short loc_18000870D
0x180008705  mov     [rax], rcx
0x180008708  xor     r8d, r8d
0x18000870b  jmp     short loc_180008719
0x18000870d  mov     [rax], rcx
0x180008710  mov     r8d, 2
0x180008716  movzx   ecx, word ptr [rcx]
0x180008719  mov     [rax+8], ecx
0x18000871c  mov     [rax+0Ch], r8d
0x180008720  xor     r8d, r8d; ActivityId
0x180008723  mov     rcx, cs:Microsoft_Windows_MediaFoundation_Performance_Context; RegHandle
0x18000872a  mov     [rsp+38h+UserData], rax; UserData
0x18000872f  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x180008734  xor     r9d, r9d; RelatedActivityId
0x180008737  call    cs:__imp_EventWriteTransfer
0x18000873d  add     rsp, 38h
0x180008741  retn
```
