# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)

- ea: `0x140001380`
- end: `0x14000143e`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapperByVal@$00@@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapperByVal@$00@@3AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `190`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140013cd0`

## callees

- `0x140001008`
- `0x140008660`

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
0x140001380  push    rbp
0x140001382  lea     rbp, [rsp-1Fh]
0x140001387  sub     rsp, 0D0h
0x14000138e  mov     rax, cs:__security_cookie
0x140001395  xor     rax, rsp
0x140001398  mov     [rbp+1Fh+var_10], rax
0x14000139c  mov     rax, [rbp+1Fh+arg_50]
0x1400013a0  xor     r9d, r9d
0x1400013a3  mov     [rbp+1Fh+var_20], rax
0x1400013a7  xor     r8d, r8d
0x1400013aa  mov     rax, [rbp+1Fh+arg_48]
0x1400013ae  mov     [rbp+1Fh+var_30], rax
0x1400013b2  mov     rax, [rbp+1Fh+arg_40]
0x1400013b6  mov     [rbp+1Fh+var_40], rax
0x1400013ba  mov     rax, [rbp+1Fh+arg_38]
0x1400013be  mov     [rbp+1Fh+var_50], rax
0x1400013c2  mov     rax, [rbp+1Fh+arg_30]
0x1400013c6  mov     [rbp+1Fh+var_60], rax
0x1400013ca  mov     rax, [rbp+1Fh+arg_28]
0x1400013ce  mov     [rbp+1Fh+var_70], rax
0x1400013d2  mov     rax, [rbp+1Fh+arg_20]
0x1400013d6  mov     [rbp+1Fh+var_80], rax
0x1400013da  lea     rax, [rsp+0D0h+var_A0]
0x1400013df  mov     [rsp+0D0h+var_A8], rax
0x1400013e4  mov     [rsp+0D0h+var_B0], 9
0x1400013ec  mov     [rbp+1Fh+var_18], 8
0x1400013f4  mov     [rbp+1Fh+var_28], 4
0x1400013fc  mov     [rbp+1Fh+var_38], 1
0x140001404  mov     [rbp+1Fh+var_48], 2
0x14000140c  mov     [rbp+1Fh+var_58], 4
0x140001414  mov     [rbp+1Fh+var_68], 4
0x14000141c  mov     [rbp+1Fh+var_78], 4
0x140001424  call    _tlgWriteTransfer_EventWriteTransfer
0x140001429  mov     rcx, [rbp+1Fh+var_10]
0x14000142d  xor     rcx, rsp; StackCookie
0x140001430  call    __security_check_cookie
0x140001435  add     rsp, 0D0h
0x14000143c  pop     rbp
0x14000143d  retn
```
