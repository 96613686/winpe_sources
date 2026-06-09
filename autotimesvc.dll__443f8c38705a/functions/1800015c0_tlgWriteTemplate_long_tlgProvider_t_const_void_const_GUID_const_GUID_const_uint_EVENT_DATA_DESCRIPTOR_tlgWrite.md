# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)

- ea: `0x1800015c0`
- end: `0x180001667`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByRef@$0BA@@@U1@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByRef@$0BA@@@33AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `167`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c450`

## callees

- `0x180001054`
- `0x180002a70`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2)
{
  return tlgWriteTransfer_EventWriteTransfer(&dword_18001C010, a2, 0, 0);
}

```

## disassembly

```asm
0x1800015c0  push    rbp
0x1800015c2  lea     rbp, [rsp-2Fh]
0x1800015c7  sub     rsp, 0B0h
0x1800015ce  mov     rax, cs:__security_cookie
0x1800015d5  xor     rax, rsp
0x1800015d8  mov     [rbp+2Fh+var_10], rax
0x1800015dc  mov     rax, [rbp+2Fh+arg_40]
0x1800015e0  xor     r9d, r9d
0x1800015e3  mov     [rbp+2Fh+var_20], rax
0x1800015e7  xor     r8d, r8d
0x1800015ea  mov     rax, [rbp+2Fh+arg_38]
0x1800015ee  mov     [rbp+2Fh+var_30], rax
0x1800015f2  mov     rax, [rbp+2Fh+arg_30]
0x1800015f6  mov     [rbp+2Fh+var_40], rax
0x1800015fa  mov     rax, [rbp+2Fh+arg_28]
0x1800015fe  mov     [rbp+2Fh+var_18], 4
0x180001606  mov     [rbp+2Fh+var_28], 8
0x18000160e  mov     [rbp+2Fh+var_38], 8
0x180001616  mov     rcx, [rax]
0x180001619  mov     rax, [rbp+2Fh+arg_20]
0x18000161d  mov     [rbp+2Fh+var_60], rax
0x180001621  lea     rax, [rbp+2Fh+var_80]
0x180001625  mov     [rbp+2Fh+var_50], rcx
0x180001629  lea     rcx, dword_18001C010
0x180001630  mov     [rsp+0B0h+var_88], rax
0x180001635  mov     [rsp+0B0h+var_90], 7
0x18000163d  mov     [rbp+2Fh+var_48], 10h
0x180001645  mov     [rbp+2Fh+var_58], 8
0x18000164d  call    _tlgWriteTransfer_EventWriteTransfer
0x180001652  mov     rcx, [rbp+2Fh+var_10]
0x180001656  xor     rcx, rsp; StackCookie
0x180001659  call    __security_check_cookie
0x18000165e  add     rsp, 0B0h
0x180001665  pop     rbp
0x180001666  retn
```
