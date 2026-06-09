# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)

- ea: `0x140001218`
- end: `0x14000126c`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `84`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000458c`
- `0x14000775c`

## callees

- `0x1400013e8`
- `0x140013b10`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2)
{
  return tlgWriteTransfer_EventWriteTransfer(a1, a2);
}

```

## disassembly

```asm
0x140001218  mov     r11, rsp
0x14000121b  sub     rsp, 78h
0x14000121f  mov     rax, cs:__security_cookie
0x140001226  xor     rax, rsp
0x140001229  mov     [rsp+78h+var_18], rax
0x14000122e  mov     rax, [rsp+78h+arg_20]
0x140001236  xor     r9d, r9d
0x140001239  mov     [r11-28h], rax
0x14000123d  lea     rax, [r11-48h]
0x140001241  mov     [r11-50h], rax
0x140001245  mov     [rsp+78h+var_58], 3
0x14000124d  mov     qword ptr [r11-20h], 4
0x140001255  call    _tlgWriteTransfer_EventWriteTransfer
0x14000125a  mov     rcx, [rsp+78h+var_18]
0x14000125f  xor     rcx, rsp; StackCookie
0x140001262  call    __security_check_cookie
0x140001267  add     rsp, 78h
0x14000126b  retn
```
