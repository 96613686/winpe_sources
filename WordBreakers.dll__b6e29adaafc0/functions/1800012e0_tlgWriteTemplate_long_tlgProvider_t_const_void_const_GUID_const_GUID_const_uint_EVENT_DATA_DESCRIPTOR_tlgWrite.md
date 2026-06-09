# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)

- ea: `0x1800012e0`
- end: `0x18000139e`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapperByVal@$00@@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapperByVal@$00@@3AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `190`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180008340`

## callees

- `0x180001a8c`
- `0x18000b640`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        __int64 a1,
        __int64 a2)
{
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0);
}

```

## disassembly

```asm
0x1800012e0  push    rbp
0x1800012e2  lea     rbp, [rsp-1Fh]
0x1800012e7  sub     rsp, 0D0h
0x1800012ee  mov     rax, cs:__security_cookie
0x1800012f5  xor     rax, rsp
0x1800012f8  mov     [rbp+1Fh+var_10], rax
0x1800012fc  mov     rax, [rbp+1Fh+arg_50]
0x180001300  xor     r9d, r9d
0x180001303  mov     [rbp+1Fh+var_20], rax
0x180001307  xor     r8d, r8d
0x18000130a  mov     rax, [rbp+1Fh+arg_48]
0x18000130e  mov     [rbp+1Fh+var_30], rax
0x180001312  mov     rax, [rbp+1Fh+arg_40]
0x180001316  mov     [rbp+1Fh+var_40], rax
0x18000131a  mov     rax, [rbp+1Fh+arg_38]
0x18000131e  mov     [rbp+1Fh+var_50], rax
0x180001322  mov     rax, [rbp+1Fh+arg_30]
0x180001326  mov     [rbp+1Fh+var_60], rax
0x18000132a  mov     rax, [rbp+1Fh+arg_28]
0x18000132e  mov     [rbp+1Fh+var_70], rax
0x180001332  mov     rax, [rbp+1Fh+arg_20]
0x180001336  mov     [rbp+1Fh+var_80], rax
0x18000133a  lea     rax, [rsp+0D0h+var_A0]
0x18000133f  mov     [rsp+0D0h+var_A8], rax
0x180001344  mov     [rsp+0D0h+var_B0], 9
0x18000134c  mov     [rbp+1Fh+var_18], 8
0x180001354  mov     [rbp+1Fh+var_28], 4
0x18000135c  mov     [rbp+1Fh+var_38], 1
0x180001364  mov     [rbp+1Fh+var_48], 2
0x18000136c  mov     [rbp+1Fh+var_58], 4
0x180001374  mov     [rbp+1Fh+var_68], 4
0x18000137c  mov     [rbp+1Fh+var_78], 4
0x180001384  call    _tlgWriteTransfer_EventWriteTransfer
0x180001389  mov     rcx, [rbp+1Fh+var_10]
0x18000138d  xor     rcx, rsp; StackCookie
0x180001390  call    __security_check_cookie
0x180001395  add     rsp, 0D0h
0x18000139c  pop     rbp
0x18000139d  retn
```
