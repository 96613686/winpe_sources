# SmsCapabilityHandler::AccessCheck(ushort const *,ushort const *,ushort const *,ulong,ushort const *,CapabilityHandlerAccessStatus *)

- ea: `0x180004330`
- end: `0x180004380`
- name: `?AccessCheck@SmsCapabilityHandler@@UEAAJPEBG00K0PEAW4CapabilityHandlerAccessStatus@@@Z`
- size: `80`
- prototype: `__int64 __fastcall(SmsCapabilityHandler *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const unsigned __int16 *, enum CapabilityHandlerAccessStatus *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180004330`
- `0x180004388`
- `0x18000f88c`

## pseudocode

```c
__int64 __fastcall SmsCapabilityHandler::AccessCheck(
        SmsCapabilityHandler *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        const unsigned __int16 *a6,
        enum CapabilityHandlerAccessStatus *a7)
{
  int v7; // eax
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *(_DWORD *)a7 = 1;
  if ( a6 )
  {
    v7 = SmsCapabilityHandler::PrivilegedAppAccessCheck(this, a5, a4);
    if ( v7 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1B,
        (unsigned int)"onecore\\base\\devices\\cam\\handler\\sms\\smscapabilityhandler.cpp",
        (const char *)(unsigned int)v7,
        v9);
      *(_DWORD *)a7 = 0;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180004330  push    rbx; int
0x180004332  sub     rsp, 20h
0x180004336  cmp     [rsp+28h+arg_28], 0
0x18000433c  mov     rbx, [rsp+28h+arg_30]
0x180004341  mov     dword ptr [rbx], 1
0x180004347  jz      short loc_180004378
0x180004349  mov     edx, [rsp+28h+arg_20]; unsigned int
0x18000434d  mov     r8, r9; unsigned __int16 *
0x180004350  call    ?PrivilegedAppAccessCheck@SmsCapabilityHandler@@AEAAJKPEBG@Z; SmsCapabilityHandler::PrivilegedAppAccessCheck(ulong,ushort const *)
0x180004355  test    eax, eax
0x180004357  jns     short loc_180004378
0x180004359  mov     rcx, [rsp+28h]; this
0x18000435e  lea     r8, aOnecoreBaseDev_0; "onecore\\base\\devices\\cam\\handler\\s"...
0x180004365  mov     r9d, eax; char *
0x180004368  mov     edx, 1Bh; void *
0x18000436d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180004372  mov     dword ptr [rbx], 0
0x180004378  xor     eax, eax
0x18000437a  add     rsp, 20h
0x18000437e  pop     rbx
0x18000437f  retn
```
