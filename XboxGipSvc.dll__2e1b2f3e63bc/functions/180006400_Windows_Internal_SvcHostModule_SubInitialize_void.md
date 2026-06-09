# Windows::Internal::SvcHostModule::SubInitialize(void)

- ea: `0x180006400`
- end: `0x18000643b`
- name: `?SubInitialize@SvcHostModule@Internal@Windows@@MEAAJXZ`
- size: `59`
- prototype: `__int64 __fastcall(Windows::Internal::SvcHostModule *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006214`
- `0x180006400`

## import_xrefs

- `combase!__imp_CoGetSharedServiceId` at `0x18000640a`
- `combase!__imp_CoGetSharedServiceId` at `0x18000640a`

## string_xrefs

- `0x18000641b`: `onecore\internal\com\inc\comservicehelper.h`

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
0x180006400  push    rbx; int
0x180006402  sub     rsp, 20h
0x180006406  add     rcx, 38h ; '8'
0x18000640a  call    cs:__imp_CoGetSharedServiceId
0x180006410  mov     ebx, eax
0x180006412  test    eax, eax
0x180006414  jns     short loc_180006433
0x180006416  mov     rcx, [rsp+28h]; this
0x18000641b  lea     r8, aOnecoreInterna; "onecore\\internal\\com\\inc\\comservice"...
0x180006422  mov     r9d, eax; char *
0x180006425  mov     edx, 19Ch; void *
0x18000642a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000642f  mov     eax, ebx
0x180006431  jmp     short loc_180006435
0x180006433  xor     eax, eax
0x180006435  add     rsp, 20h
0x180006439  pop     rbx
0x18000643a  retn
```
