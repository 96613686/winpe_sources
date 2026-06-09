# Windows::Internal::SvcHostModule::SubInitialize(void)

- ea: `0x180008d50`
- end: `0x180008d8b`
- name: `?SubInitialize@SvcHostModule@Internal@Windows@@MEAAJXZ`
- size: `59`
- prototype: `int(Windows::Internal::SvcHostModule *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180008a38`
- `0x180008d50`

## import_xrefs

- `combase!__imp_CoGetSharedServiceId` at `0x180008d5a`
- `combase!__imp_CoGetSharedServiceId` at `0x180008d5a`

## string_xrefs

- `0x180008d6b`: `onecore\internal\com\inc\comservicehelper.h`

## pseudocode

```c
__int64 __fastcall Windows::Internal::SvcHostModule::SubInitialize(Windows::Internal::SvcHostModule *this)
{
  int SharedServiceId; // eax
  unsigned int v2; // ebx
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  SharedServiceId = CoGetSharedServiceId((char *)this + 56);
  v2 = SharedServiceId;
  if ( SharedServiceId >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x19C,
    (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
    (const char *)(unsigned int)SharedServiceId,
    v4);
  return v2;
}

```

## disassembly

```asm
0x180008d50  push    rbx; int
0x180008d52  sub     rsp, 20h
0x180008d56  add     rcx, 38h ; '8'
0x180008d5a  call    cs:__imp_CoGetSharedServiceId
0x180008d60  mov     ebx, eax
0x180008d62  test    eax, eax
0x180008d64  jns     short loc_180008D83
0x180008d66  mov     rcx, [rsp+28h]; this
0x180008d6b  lea     r8, aOnecoreInterna_0; "onecore\\internal\\com\\inc\\comservice"...
0x180008d72  mov     r9d, eax; char *
0x180008d75  mov     edx, 19Ch; void *
0x180008d7a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008d7f  mov     eax, ebx
0x180008d81  jmp     short loc_180008D85
0x180008d83  xor     eax, eax
0x180008d85  add     rsp, 20h
0x180008d89  pop     rbx
0x180008d8a  retn
```
