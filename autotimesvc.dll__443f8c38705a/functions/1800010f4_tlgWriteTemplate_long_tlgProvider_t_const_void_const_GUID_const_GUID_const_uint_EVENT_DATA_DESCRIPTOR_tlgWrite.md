# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<1> const &)

- ea: `0x1800010f4`
- end: `0x180001148`
- name: `??$Write@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$00@@@Z`
- size: `84`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000891c`
- `0x180009934`
- `0x18000edd8`
- `0x180010800`

## callees

- `0x180001054`
- `0x180002a70`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0);
}

```

## disassembly

```asm
0x1800010f4  mov     r11, rsp
0x1800010f7  sub     rsp, 78h
0x1800010fb  mov     rax, cs:__security_cookie
0x180001102  xor     rax, rsp
0x180001105  mov     [rsp+78h+var_18], rax
0x18000110a  mov     rax, [rsp+78h+arg_20]
0x180001112  xor     r9d, r9d
0x180001115  mov     [r11-28h], rax
0x180001119  lea     rax, [r11-48h]
0x18000111d  mov     [r11-50h], rax
0x180001121  mov     [rsp+78h+var_58], 3
0x180001129  mov     qword ptr [r11-20h], 1
0x180001131  call    _tlgWriteTransfer_EventWriteTransfer
0x180001136  mov     rcx, [rsp+78h+var_18]
0x18000113b  xor     rcx, rsp; StackCookie
0x18000113e  call    __security_check_cookie
0x180001143  add     rsp, 78h
0x180001147  retn
```
