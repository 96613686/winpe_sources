# McGenEventWrite_EventWriteTransfer

- ea: `0x18000c224`
- end: `0x18000c276`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, __int64, ULONG UserDataCount, PEVENT_DATA_DESCRIPTOR UserData)`
- caller_count: `40`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000b8c0`
- `0x18000ba4c`
- `0x18000bed4`
- `0x18000c27c`
- `0x18000c450`
- `0x18000c590`
- `0x18000c7d0`
- `0x18000c9dc`
- `0x18000cb48`
- `0x18000ccd0`
- `0x18000ce30`
- `0x18000ea3c`
- `0x18000f668`
- `0x18000fdf0`
- `0x18001088c`
- `0x180010e6c`
- `0x180011134`
- `0x180011400`
- `0x1800122a0`
- `0x180012388`
- `0x180012430`
- `0x1800128d0`
- `0x1800133ac`
- `0x180013720`
- `0x180014344`
- `0x18001468c`
- `0x180015340`
- `0x1800156dc`
- `0x180016094`
- `0x1800163d0`
- `0x18001667c`
- `0x180016860`
- `0x180016a94`
- `0x1800171d0`
- `0x1800172a4`
- `0x180017bb0`
- `0x18001838f`
- `0x180018467`
- `0x180018558`
- `0x1800185cb`

## callees

- `0x18000c224`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000c26b`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000c26b`

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

  v5 = (unsigned __int16 *)qword_180023008;
  if ( qword_180023008 )
  {
    UserData->Ptr = qword_180023008;
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
  return EventWriteTransfer(S_Microsoft_Windows_IPxlatCfg_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x18000c224  sub     rsp, 38h
0x18000c228  mov     rcx, cs:qword_180023008
0x18000c22f  mov     rax, [rsp+38h+arg_20]
0x18000c234  test    rcx, rcx
0x18000c237  jnz     short loc_18000C241
0x18000c239  mov     [rax], rcx
0x18000c23c  xor     r8d, r8d
0x18000c23f  jmp     short loc_18000C24D
0x18000c241  mov     [rax], rcx
0x18000c244  mov     r8d, 2
0x18000c24a  movzx   ecx, word ptr [rcx]
0x18000c24d  mov     [rax+8], ecx
0x18000c250  mov     [rax+0Ch], r8d
0x18000c254  xor     r8d, r8d; ActivityId
0x18000c257  mov     rcx, cs:S_Microsoft_Windows_IPxlatCfg_Context; RegHandle
0x18000c25e  mov     [rsp+38h+UserData], rax; UserData
0x18000c263  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18000c268  xor     r9d, r9d; RelatedActivityId
0x18000c26b  call    cs:__imp_EventWriteTransfer
0x18000c271  add     rsp, 38h
0x18000c275  retn
```
