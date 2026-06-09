# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001524`
- end: `0x1800015b8`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@44@Z`
- size: `148`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000bf30`

## callees

- `0x180001054`
- `0x180002a70`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2)
{
  return tlgWriteTransfer_EventWriteTransfer(&dword_18001C010, a2, 0, 0);
}

```

## disassembly

```asm
0x180001524  push    rbp
0x180001526  lea     rbp, [rsp-37h]
0x18000152b  sub     rsp, 0A0h
0x180001532  mov     rax, cs:__security_cookie
0x180001539  xor     rax, rsp
0x18000153c  mov     [rbp+37h+var_10], rax
0x180001540  mov     rax, [rbp+37h+arg_38]
0x180001544  lea     rcx, dword_18001C010
0x18000154b  mov     [rbp+37h+var_20], rax
0x18000154f  xor     r9d, r9d
0x180001552  mov     rax, [rbp+37h+arg_30]
0x180001556  xor     r8d, r8d
0x180001559  mov     [rbp+37h+var_30], rax
0x18000155d  mov     rax, [rbp+37h+arg_28]
0x180001561  mov     [rbp+37h+var_40], rax
0x180001565  mov     rax, [rbp+37h+arg_20]
0x180001569  mov     [rbp+37h+var_50], rax
0x18000156d  lea     rax, [rbp+37h+var_70]
0x180001571  mov     [rsp+0A0h+var_78], rax
0x180001576  mov     [rsp+0A0h+var_80], 6
0x18000157e  mov     [rbp+37h+var_18], 4
0x180001586  mov     [rbp+37h+var_28], 4
0x18000158e  mov     [rbp+37h+var_38], 4
0x180001596  mov     [rbp+37h+var_48], 8
0x18000159e  call    _tlgWriteTransfer_EventWriteTransfer
0x1800015a3  mov     rcx, [rbp+37h+var_10]
0x1800015a7  xor     rcx, rsp; StackCookie
0x1800015aa  call    __security_check_cookie
0x1800015af  add     rsp, 0A0h
0x1800015b6  pop     rbp
0x1800015b7  retn
```
