# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x18000148c`
- end: `0x18000151e`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z`
- size: `146`
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
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2)
{
  return tlgWriteTransfer_EventWriteTransfer(&dword_18001C010, a2, 0, 0);
}

```

## disassembly

```asm
0x18000148c  mov     r11, rsp
0x18000148f  sub     rsp, 98h
0x180001496  mov     rax, cs:__security_cookie
0x18000149d  xor     rax, rsp
0x1800014a0  mov     [rsp+98h+var_18], rax
0x1800014a8  mov     rax, [rsp+98h+arg_30]
0x1800014b0  lea     rcx, dword_18001C010
0x1800014b7  mov     [r11-28h], rax
0x1800014bb  xor     r9d, r9d
0x1800014be  mov     rax, [rsp+98h+arg_28]
0x1800014c6  xor     r8d, r8d
0x1800014c9  mov     [r11-38h], rax
0x1800014cd  mov     rax, [rsp+98h+arg_20]
0x1800014d5  mov     [r11-48h], rax
0x1800014d9  lea     rax, [r11-68h]
0x1800014dd  mov     [r11-70h], rax
0x1800014e1  mov     [rsp+98h+var_78], 5
0x1800014e9  mov     qword ptr [r11-20h], 4
0x1800014f1  mov     qword ptr [r11-30h], 4
0x1800014f9  mov     qword ptr [r11-40h], 8
0x180001501  call    _tlgWriteTransfer_EventWriteTransfer
0x180001506  mov     rcx, [rsp+98h+var_18]
0x18000150e  xor     rcx, rsp; StackCookie
0x180001511  call    __security_check_cookie
0x180001516  add     rsp, 98h
0x18000151d  retn
```
