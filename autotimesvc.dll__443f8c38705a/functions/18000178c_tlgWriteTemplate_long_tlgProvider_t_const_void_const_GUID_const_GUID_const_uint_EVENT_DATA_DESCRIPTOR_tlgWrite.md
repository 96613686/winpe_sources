# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)

- ea: `0x18000178c`
- end: `0x180001830`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3333@Z`
- size: `164`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000cc10`

## callees

- `0x180001054`
- `0x180002a70`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        __int64 a1,
        __int64 a2)
{
  return tlgWriteTransfer_EventWriteTransfer(&dword_18001C010, a2, 0, 0);
}

```

## disassembly

```asm
0x18000178c  push    rbp
0x18000178e  lea     rbp, [rsp-2Fh]
0x180001793  sub     rsp, 0B0h
0x18000179a  mov     rax, cs:__security_cookie
0x1800017a1  xor     rax, rsp
0x1800017a4  mov     [rbp+2Fh+var_10], rax
0x1800017a8  mov     rax, [rbp+2Fh+arg_40]
0x1800017ac  lea     rcx, dword_18001C010
0x1800017b3  mov     [rbp+2Fh+var_20], rax
0x1800017b7  xor     r9d, r9d
0x1800017ba  mov     rax, [rbp+2Fh+arg_38]
0x1800017be  xor     r8d, r8d
0x1800017c1  mov     [rbp+2Fh+var_30], rax
0x1800017c5  mov     rax, [rbp+2Fh+arg_30]
0x1800017c9  mov     [rbp+2Fh+var_40], rax
0x1800017cd  mov     rax, [rbp+2Fh+arg_28]
0x1800017d1  mov     [rbp+2Fh+var_50], rax
0x1800017d5  mov     rax, [rbp+2Fh+arg_20]
0x1800017d9  mov     [rbp+2Fh+var_60], rax
0x1800017dd  lea     rax, [rbp+2Fh+var_80]
0x1800017e1  mov     [rsp+0B0h+var_88], rax
0x1800017e6  mov     [rsp+0B0h+var_90], 7
0x1800017ee  mov     [rbp+2Fh+var_18], 8
0x1800017f6  mov     [rbp+2Fh+var_28], 8
0x1800017fe  mov     [rbp+2Fh+var_38], 8
0x180001806  mov     [rbp+2Fh+var_48], 8
0x18000180e  mov     [rbp+2Fh+var_58], 8
0x180001816  call    _tlgWriteTransfer_EventWriteTransfer
0x18000181b  mov     rcx, [rbp+2Fh+var_10]
0x18000181f  xor     rcx, rsp; StackCookie
0x180001822  call    __security_check_cookie
0x180001827  add     rsp, 0B0h
0x18000182e  pop     rbp
0x18000182f  retn
```
