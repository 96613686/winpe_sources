# Windows::Internal::SvcHostModule::SubInitialize(void)

- ea: `0x180009970`
- end: `0x1800099ab`
- name: `?SubInitialize@SvcHostModule@Internal@Windows@@MEAAJXZ`
- size: `59`
- prototype: `int(Windows::Internal::SvcHostModule *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000907c`
- `0x180009970`

## import_xrefs

- `combase!__imp_CoGetSharedServiceId` at `0x18000997a`
- `combase!__imp_CoGetSharedServiceId` at `0x18000997a`

## string_xrefs

- `0x18000998b`: `onecore\internal\com\inc\comservicehelper.h`

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
0x180009970  push    rbx; int
0x180009972  sub     rsp, 20h
0x180009976  add     rcx, 38h ; '8'
0x18000997a  call    cs:__imp_CoGetSharedServiceId
0x180009980  mov     ebx, eax
0x180009982  test    eax, eax
0x180009984  jns     short loc_1800099A3
0x180009986  mov     rcx, [rsp+28h]; this
0x18000998b  lea     r8, aOnecoreInterna_0; "onecore\\internal\\com\\inc\\comservice"...
0x180009992  mov     r9d, eax; char *
0x180009995  mov     edx, 19Ch; void *
0x18000999a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000999f  mov     eax, ebx
0x1800099a1  jmp     short loc_1800099A5
0x1800099a3  xor     eax, eax
0x1800099a5  add     rsp, 20h
0x1800099a9  pop     rbx
0x1800099aa  retn
```
