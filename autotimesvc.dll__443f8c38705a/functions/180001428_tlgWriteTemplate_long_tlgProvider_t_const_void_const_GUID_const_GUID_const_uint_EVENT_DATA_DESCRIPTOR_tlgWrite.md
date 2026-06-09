# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)

- ea: `0x180001428`
- end: `0x180001486`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `94`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000bd34`
- `0x18000bea8`
- `0x18000c6a8`

## callees

- `0x180001054`
- `0x180002a70`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
        __int64 a1,
        __int64 a2)
{
  return tlgWriteTransfer_EventWriteTransfer(&dword_18001C010, a2, 0, 0);
}

```

## disassembly

```asm
0x180001428  mov     r11, rsp
0x18000142b  sub     rsp, 78h
0x18000142f  mov     rax, cs:__security_cookie
0x180001436  xor     rax, rsp
0x180001439  mov     [rsp+78h+var_18], rax
0x18000143e  mov     rax, [rsp+78h+arg_20]
0x180001446  lea     rcx, dword_18001C010
0x18000144d  mov     [r11-28h], rax
0x180001451  xor     r9d, r9d
0x180001454  lea     rax, [r11-48h]
0x180001458  mov     qword ptr [r11-20h], 8
0x180001460  mov     [r11-50h], rax
0x180001464  xor     r8d, r8d
0x180001467  mov     [rsp+78h+var_58], 3
0x18000146f  call    _tlgWriteTransfer_EventWriteTransfer
0x180001474  mov     rcx, [rsp+78h+var_18]
0x180001479  xor     rcx, rsp; StackCookie
0x18000147c  call    __security_check_cookie
0x180001481  add     rsp, 78h
0x180001485  retn
```
