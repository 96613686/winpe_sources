# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)

- ea: `0x1800018b4`
- end: `0x18000192c`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3@Z`
- size: `120`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000cf10`

## callees

- `0x180001054`
- `0x180002a70`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        __int64 a1,
        __int64 a2)
{
  return tlgWriteTransfer_EventWriteTransfer(&dword_18001C010, a2, 0, 0);
}

```

## disassembly

```asm
0x1800018b4  mov     r11, rsp
0x1800018b7  sub     rsp, 88h
0x1800018be  mov     rax, cs:__security_cookie
0x1800018c5  xor     rax, rsp
0x1800018c8  mov     [rsp+88h+var_18], rax
0x1800018cd  mov     rax, [rsp+88h+arg_28]
0x1800018d5  lea     rcx, dword_18001C010
0x1800018dc  mov     [r11-28h], rax
0x1800018e0  xor     r9d, r9d
0x1800018e3  mov     rax, [rsp+88h+arg_20]
0x1800018eb  xor     r8d, r8d
0x1800018ee  mov     [r11-38h], rax
0x1800018f2  lea     rax, [r11-58h]
0x1800018f6  mov     [r11-60h], rax
0x1800018fa  mov     [rsp+88h+var_68], 4
0x180001902  mov     qword ptr [r11-20h], 8
0x18000190a  mov     qword ptr [r11-30h], 8
0x180001912  call    _tlgWriteTransfer_EventWriteTransfer
0x180001917  mov     rcx, [rsp+88h+var_18]
0x18000191c  xor     rcx, rsp; StackCookie
0x18000191f  call    __security_check_cookie
0x180001924  add     rsp, 88h
0x18000192b  retn
```
