# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)

- ea: `0x180001218`
- end: `0x180001269`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `81`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `16`
- callee_count: `2`
- tags: ``

## callers

- `0x180005f40`
- `0x180006350`
- `0x180008100`
- `0x1800084c4`
- `0x180008798`
- `0x180009d88`
- `0x18000af0c`
- `0x18000b118`
- `0x18000b668`
- `0x18000c7ac`
- `0x18000d0ec`
- `0x18000d178`
- `0x18000d330`
- `0x180010068`
- `0x180010578`
- `0x180010800`

## callees

- `0x180001054`
- `0x180002a70`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001218  mov     r11, rsp
0x18000121b  sub     rsp, 78h
0x18000121f  mov     rax, cs:__security_cookie
0x180001226  xor     rax, rsp
0x180001229  mov     [rsp+78h+var_18], rax
0x18000122e  mov     rax, [rsp+78h+arg_20]
0x180001236  mov     [r11-28h], rax
0x18000123a  lea     rax, [r11-48h]
0x18000123e  mov     [r11-50h], rax
0x180001242  mov     [rsp+78h+var_58], 3
0x18000124a  mov     qword ptr [r11-20h], 4
0x180001252  call    _tlgWriteTransfer_EventWriteTransfer
0x180001257  mov     rcx, [rsp+78h+var_18]
0x18000125c  xor     rcx, rsp; StackCookie
0x18000125f  call    __security_check_cookie
0x180001264  add     rsp, 78h
0x180001268  retn
```
