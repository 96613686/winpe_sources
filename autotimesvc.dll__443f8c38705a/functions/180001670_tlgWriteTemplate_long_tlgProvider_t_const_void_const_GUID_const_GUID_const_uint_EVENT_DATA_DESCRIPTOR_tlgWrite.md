# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001670`
- end: `0x1800016e9`
- name: `??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000caf0`

## callees

- `0x180001054`
- `0x180002a70`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2)
{
  return tlgWriteTransfer_EventWriteTransfer(&dword_18001C010, a2, 0, 0);
}

```

## disassembly

```asm
0x180001670  mov     r11, rsp
0x180001673  sub     rsp, 88h
0x18000167a  mov     rax, cs:__security_cookie
0x180001681  xor     rax, rsp
0x180001684  mov     [rsp+88h+var_18], rax
0x180001689  mov     rax, [rsp+88h+arg_28]
0x180001691  mov     r8d, 4
0x180001697  mov     [r11-28h], rax
0x18000169b  xor     r9d, r9d
0x18000169e  mov     rax, [rsp+88h+arg_20]
0x1800016a6  mov     [r11-20h], r8
0x1800016aa  mov     qword ptr [r11-30h], 10h
0x1800016b2  mov     rcx, [rax]
0x1800016b5  lea     rax, [r11-58h]
0x1800016b9  mov     [r11-60h], rax
0x1800016bd  mov     [r11-68h], r8d
0x1800016c1  xor     r8d, r8d
0x1800016c4  mov     [r11-38h], rcx
0x1800016c8  lea     rcx, dword_18001C010
0x1800016cf  call    _tlgWriteTransfer_EventWriteTransfer
0x1800016d4  mov     rcx, [rsp+88h+var_18]
0x1800016d9  xor     rcx, rsp; StackCookie
0x1800016dc  call    __security_check_cookie
0x1800016e1  add     rsp, 88h
0x1800016e8  retn
```
