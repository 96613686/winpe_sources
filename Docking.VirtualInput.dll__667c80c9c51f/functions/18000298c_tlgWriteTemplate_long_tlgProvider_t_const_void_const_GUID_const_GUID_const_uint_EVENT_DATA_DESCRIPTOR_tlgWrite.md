# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x18000298c`
- end: `0x180002a42`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333@Z`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000db08`

## callees

- `0x180001c98`
- `0x180001db4`
- `0x1800036a0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        const GUID *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  struct _EVENT_DATA_DESCRIPTOR v9; // [rsp+40h] [rbp-78h] BYREF
  char v10; // [rsp+60h] [rbp-58h] BYREF

  _tlgDataDescInit<_tlgIndexSequence<4,0,1,2,3>>::Fill<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
    (unsigned int)&v10,
    a5,
    a6,
    a7,
    a8);
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, a4, 6u, &v9);
}

```

## disassembly

```asm
0x18000298c  mov     [rsp+arg_18], r9
0x180002991  mov     [rsp+arg_10], r8
0x180002996  mov     [rsp+arg_8], rdx
0x18000299b  mov     [rsp+arg_0], rcx
0x1800029a0  sub     rsp, 0B8h
0x1800029a7  mov     rax, cs:__security_cookie
0x1800029ae  xor     rax, rsp
0x1800029b1  mov     [rsp+0B8h+var_18], rax
0x1800029b9  mov     [rsp+0B8h+var_88], 6
0x1800029c1  lea     rax, [rsp+0B8h+var_58]
0x1800029c6  mov     rcx, [rsp+0B8h+arg_38]
0x1800029ce  mov     [rsp+0B8h+var_98], rcx
0x1800029d3  mov     r9, [rsp+0B8h+arg_30]
0x1800029db  mov     r8, [rsp+0B8h+arg_28]
0x1800029e3  mov     rdx, [rsp+0B8h+arg_20]
0x1800029eb  mov     rcx, rax
0x1800029ee  call    ??$Fill@U?$_tlgWrapperByVal@$03@@U1@U1@U1@@?$_tlgDataDescInit@U?$_tlgIndexSequence@$03$0A@$00$01$02@@@@SAXPEAU_EVENT_DATA_DESCRIPTOR@@AEBU?$_tlgWrapperByVal@$03@@111@Z
0x1800029f3  lea     rax, [rsp+0B8h+var_78]
0x1800029f8  mov     [rsp+0B8h+var_90], rax
0x1800029fd  mov     dword ptr [rsp+0B8h+var_98], 6
0x180002a05  mov     r9, [rsp+0B8h+arg_18]
0x180002a0d  mov     r8, [rsp+0B8h+arg_10]
0x180002a15  mov     rdx, [rsp+0B8h+arg_8]
0x180002a1d  mov     rcx, [rsp+0B8h+arg_0]
0x180002a25  call    _tlgWriteTransfer_EventWriteTransfer
0x180002a2a  mov     rcx, [rsp+0B8h+var_18]
0x180002a32  xor     rcx, rsp; StackCookie
0x180002a35  call    __security_check_cookie
0x180002a3a  add     rsp, 0B8h
0x180002a41  retn
```
