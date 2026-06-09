# McGenEventWrite_EventWriteTransfer

- ea: `0x18008cc78`
- end: `0x18008ccca`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: ``
- caller_count: `74`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007550`
- `0x180009930`
- `0x180009dc0`
- `0x180012b40`
- `0x18001509c`
- `0x18001b6c0`
- `0x18001c6d0`
- `0x18001c888`
- `0x18001cd20`
- `0x18001e760`
- `0x180021f44`
- `0x1800226e8`
- `0x180022e0c`
- `0x180023144`
- `0x180023288`
- `0x180027464`
- `0x180029104`
- `0x180029f60`
- `0x180030828`
- `0x18003455c`
- `0x180034ed0`
- `0x180036108`
- `0x18003c4b4`
- `0x18003cbe8`
- `0x18004bd90`
- `0x180051c90`
- `0x18005ca5c`
- `0x18005da8c`
- `0x180061864`
- `0x180061f60`
- `0x180062130`
- `0x180062790`
- `0x1800630bc`
- `0x18006cb0c`
- `0x180077058`
- `0x180077724`
- `0x180079414`
- `0x18007a3d0`
- `0x18007a7dc`
- `0x18007b638`
- `0x18007e4a8`
- `0x1800817a8`
- `0x18008c94c`
- `0x18008c9f4`
- `0x18008ca4c`
- `0x18008cab8`
- `0x18008cb30`
- `0x18008cb9c`
- `0x18008cc1c`
- `0x1800a26b0`

## callees

- `0x18008cc78`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18008ccbf`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18008ccbf`

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

  v5 = (unsigned __int16 *)qword_180105008;
  if ( qword_180105008 )
  {
    UserData->Ptr = qword_180105008;
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
  return EventWriteTransfer(MICROSOFT_WINDOWSPHONE_COREUI_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x18008cc78  sub     rsp, 38h
0x18008cc7c  mov     rcx, cs:qword_180105008
0x18008cc83  mov     rax, [rsp+38h+arg_20]
0x18008cc88  test    rcx, rcx
0x18008cc8b  jnz     short loc_18008CC95
0x18008cc8d  mov     [rax], rcx
0x18008cc90  xor     r8d, r8d
0x18008cc93  jmp     short loc_18008CCA1
0x18008cc95  mov     [rax], rcx
0x18008cc98  mov     r8d, 2
0x18008cc9e  movzx   ecx, word ptr [rcx]
0x18008cca1  mov     [rax+8], ecx
0x18008cca4  mov     [rax+0Ch], r8d
0x18008cca8  xor     r8d, r8d; ActivityId
0x18008ccab  mov     rcx, cs:MICROSOFT_WINDOWSPHONE_COREUI_Context; RegHandle
0x18008ccb2  mov     [rsp+38h+UserData], rax; UserData
0x18008ccb7  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18008ccbc  xor     r9d, r9d; RelatedActivityId
0x18008ccbf  call    cs:__imp_EventWriteTransfer
0x18008ccc5  add     rsp, 38h
0x18008ccc9  retn
```
