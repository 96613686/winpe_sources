# McGenEventWrite_EventWriteTransfer

- ea: `0x180007264`
- end: `0x1800072bd`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `89`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800072c4`
- `0x1800073a0`

## callees

- `0x180007264`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800072ab`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800072ab`

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

  v5 = (unsigned __int16 *)qword_180012008;
  if ( qword_180012008 )
  {
    UserData->Ptr = qword_180012008;
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
  return EventWriteTransfer(MDM_ENTERPRISE_DIAGNOSTICS_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x180007264  sub     rsp, 38h
0x180007268  mov     rcx, cs:qword_180012008
0x18000726f  mov     rax, [rsp+38h+arg_20]
0x180007274  test    rcx, rcx
0x180007277  jnz     short loc_180007281
0x180007279  mov     [rax], rcx
0x18000727c  xor     r8d, r8d
0x18000727f  jmp     short loc_18000728D
0x180007281  mov     [rax], rcx
0x180007284  mov     r8d, 2
0x18000728a  movzx   ecx, word ptr [rcx]
0x18000728d  mov     [rax+8], ecx
0x180007290  mov     [rax+0Ch], r8d
0x180007294  xor     r8d, r8d; ActivityId
0x180007297  mov     rcx, cs:MDM_ENTERPRISE_DIAGNOSTICS_Context; RegHandle
0x18000729e  mov     [rsp+38h+UserData], rax; UserData
0x1800072a3  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x1800072a8  xor     r9d, r9d; RelatedActivityId
0x1800072ab  call    cs:__imp_EventWriteTransfer
0x1800072b2  nop     dword ptr [rax+rax+00h]
0x1800072b7  add     rsp, 38h
0x1800072bb  retn
```
