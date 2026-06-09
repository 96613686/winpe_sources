# Windows::Internal::SvcHostModule::SubInitialize(void)

- ea: `0x18000cea0`
- end: `0x18000cedb`
- name: `?SubInitialize@SvcHostModule@Internal@Windows@@MEAAJXZ`
- size: `59`
- prototype: `int(Windows::Internal::SvcHostModule *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000c4cc`
- `0x18000cea0`

## import_xrefs

- `combase!__imp_CoGetSharedServiceId` at `0x18000ceaa`
- `combase!__imp_CoGetSharedServiceId` at `0x18000ceaa`

## string_xrefs

- `0x18000cebb`: `onecore\internal\com\inc\comservicehelper.h`

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
0x18000cea0  push    rbx; int
0x18000cea2  sub     rsp, 20h
0x18000cea6  add     rcx, 38h ; '8'
0x18000ceaa  call    cs:__imp_CoGetSharedServiceId
0x18000ceb0  mov     ebx, eax
0x18000ceb2  test    eax, eax
0x18000ceb4  jns     short loc_18000CED3
0x18000ceb6  mov     rcx, [rsp+28h]; this
0x18000cebb  lea     r8, aOnecoreInterna_0; "onecore\\internal\\com\\inc\\comservice"...
0x18000cec2  mov     r9d, eax; char *
0x18000cec5  mov     edx, 19Ch; void *
0x18000ceca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cecf  mov     eax, ebx
0x18000ced1  jmp     short loc_18000CED5
0x18000ced3  xor     eax, eax
0x18000ced5  add     rsp, 20h
0x18000ced9  pop     rbx
0x18000ceda  retn
```
