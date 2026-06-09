# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)

- ea: `0x18000121c`
- end: `0x18000127b`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `95`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180004950`
- `0x180006df0`
- `0x18001fc69`

## callees

- `0x1800012b8`
- `0x18001f420`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+30h] [rbp-48h] BYREF
  __int64 v7; // [rsp+50h] [rbp-28h]
  __int64 v8; // [rsp+58h] [rbp-20h]

  v7 = a5;
  v8 = 4;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_18002B000, a2, 0, 0, 3u, &v6);
}

```

## disassembly

```asm
0x18000121c  mov     r11, rsp
0x18000121f  sub     rsp, 78h
0x180001223  mov     rax, cs:__security_cookie
0x18000122a  xor     rax, rsp
0x18000122d  mov     [rsp+78h+var_18], rax
0x180001232  mov     rax, [rsp+78h+arg_20]
0x18000123a  lea     rcx, dword_18002B000
0x180001241  mov     [r11-28h], rax
0x180001245  xor     r9d, r9d
0x180001248  lea     rax, [r11-48h]
0x18000124c  mov     qword ptr [r11-20h], 4
0x180001254  mov     [r11-50h], rax
0x180001258  xor     r8d, r8d
0x18000125b  mov     [rsp+78h+var_58], 3
0x180001263  call    _tlgWriteTransfer_EventWriteTransfer
0x180001268  mov     rcx, [rsp+78h+var_18]
0x18000126d  xor     rcx, rsp; StackCookie
0x180001270  call    __security_check_cookie
0x180001275  add     rsp, 78h
0x180001279  retn
```
