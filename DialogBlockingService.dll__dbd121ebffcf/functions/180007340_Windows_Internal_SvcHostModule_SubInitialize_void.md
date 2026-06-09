# Windows::Internal::SvcHostModule::SubInitialize(void)

- ea: `0x180007340`
- end: `0x18000737b`
- name: `?SubInitialize@SvcHostModule@Internal@Windows@@MEAAJXZ`
- size: `59`
- prototype: `__int64 __fastcall(Windows::Internal::SvcHostModule *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006804`
- `0x180007340`

## import_xrefs

- `combase!__imp_CoGetSharedServiceId` at `0x18000734a`
- `combase!__imp_CoGetSharedServiceId` at `0x18000734a`

## string_xrefs

- `0x18000735b`: `onecore\internal\com\inc\comservicehelper.h`

## pseudocode

```c
__int64 __fastcall Windows::Internal::SvcHostModule::SubInitialize(Windows::Internal::SvcHostModule *this)
{
  int SharedServiceId; // eax
  unsigned int v2; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  SharedServiceId = CoGetSharedServiceId((char *)this + 56);
  v2 = SharedServiceId;
  if ( SharedServiceId >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x19C,
    (int)"onecore\\internal\\com\\inc\\comservicehelper.h",
    (const char *)(unsigned int)SharedServiceId);
  return v2;
}

```

## disassembly

```asm
0x180007340  push    rbx; int
0x180007342  sub     rsp, 20h
0x180007346  add     rcx, 38h ; '8'
0x18000734a  call    cs:__imp_CoGetSharedServiceId
0x180007350  mov     ebx, eax
0x180007352  test    eax, eax
0x180007354  jns     short loc_180007373
0x180007356  mov     rcx, [rsp+28h]; this
0x18000735b  lea     r8, aOnecoreInterna; "onecore\\internal\\com\\inc\\comservice"...
0x180007362  mov     r9d, eax; char *
0x180007365  mov     edx, 19Ch; void *
0x18000736a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000736f  mov     eax, ebx
0x180007371  jmp     short loc_180007375
0x180007373  xor     eax, eax
0x180007375  add     rsp, 20h
0x180007379  pop     rbx
0x18000737a  retn
```
