# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)

- ea: `0x180002fe0`
- end: `0x18000306d`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `141`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800171d4`

## callees

- `0x180001c98`
- `0x180002f9c`
- `0x1800036a0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        const GUID *a4,
        __int64 a5)
{
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+38h] [rbp-40h] BYREF
  _BYTE v7[16]; // [rsp+58h] [rbp-20h] BYREF

  _tlgDataDescInit<_tlgIndexSequence<1,0>>::Fill<_tlgWrapperByVal<4>>(v7, a5);
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, a4, 3u, &v6);
}

```

## disassembly

```asm
0x180002fe0  mov     [rsp+arg_18], r9
0x180002fe5  mov     [rsp+arg_10], r8
0x180002fea  mov     [rsp+arg_8], rdx
0x180002fef  mov     [rsp+arg_0], rcx
0x180002ff4  sub     rsp, 78h
0x180002ff8  mov     rax, cs:__security_cookie
0x180002fff  xor     rax, rsp
0x180003002  mov     [rsp+78h+var_10], rax
0x180003007  mov     [rsp+78h+var_48], 3
0x18000300f  lea     rax, [rsp+78h+var_20]
0x180003014  mov     rdx, [rsp+78h+arg_20]
0x18000301c  mov     rcx, rax
0x18000301f  call    ??$Fill@U?$_tlgWrapperByVal@$03@@@?$_tlgDataDescInit@U?$_tlgIndexSequence@$00$0A@@@@@SAXPEAU_EVENT_DATA_DESCRIPTOR@@AEBU?$_tlgWrapperByVal@$03@@@Z
0x180003024  lea     rax, [rsp+78h+var_40]
0x180003029  mov     [rsp+78h+var_50], rax
0x18000302e  mov     [rsp+78h+var_58], 3
0x180003036  mov     r9, [rsp+78h+arg_18]
0x18000303e  mov     r8, [rsp+78h+arg_10]
0x180003046  mov     rdx, [rsp+78h+arg_8]
0x18000304e  mov     rcx, [rsp+78h+arg_0]
0x180003056  call    _tlgWriteTransfer_EventWriteTransfer
0x18000305b  mov     rcx, [rsp+78h+var_10]
0x180003060  xor     rcx, rsp; StackCookie
0x180003063  call    __security_check_cookie
0x180003068  add     rsp, 78h
0x18000306c  retn
```
