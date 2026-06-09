# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001270`
- end: `0x1800012d8`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z`
- size: `104`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180006598`
- `0x18000b3b8`
- `0x18000c300`
- `0x18000d330`
- `0x180010ac0`

## callees

- `0x180001054`
- `0x180002a70`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0);
}

```

## disassembly

```asm
0x180001270  mov     r11, rsp
0x180001273  sub     rsp, 88h
0x18000127a  mov     rax, cs:__security_cookie
0x180001281  xor     rax, rsp
0x180001284  mov     [rsp+88h+var_18], rax
0x180001289  mov     rax, [rsp+88h+arg_28]
0x180001291  mov     r9d, 4
0x180001297  mov     [r11-28h], rax
0x18000129b  mov     rax, [rsp+88h+arg_20]
0x1800012a3  mov     [r11-38h], rax
0x1800012a7  lea     rax, [r11-58h]
0x1800012ab  mov     [r11-60h], rax
0x1800012af  mov     [r11-68h], r9d
0x1800012b3  mov     [r11-20h], r9
0x1800012b7  mov     [r11-30h], r9
0x1800012bb  xor     r9d, r9d
0x1800012be  call    _tlgWriteTransfer_EventWriteTransfer
0x1800012c3  mov     rcx, [rsp+88h+var_18]
0x1800012c8  xor     rcx, rsp; StackCookie
0x1800012cb  call    __security_check_cookie
0x1800012d0  add     rsp, 88h
0x1800012d7  retn
```
