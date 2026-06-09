# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &)

- ea: `0x1800016f0`
- end: `0x180001785`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `149`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c7ac`
- `0x18000c900`

## callees

- `0x180001054`
- `0x180002a70`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>>(
        __int64 a1,
        __int64 a2)
{
  return tlgWriteTransfer_EventWriteTransfer(&dword_18001C010, a2, 0, 0);
}

```

## disassembly

```asm
0x1800016f0  mov     r11, rsp
0x1800016f3  sub     rsp, 98h
0x1800016fa  mov     rax, cs:__security_cookie
0x180001701  xor     rax, rsp
0x180001704  mov     [rsp+98h+var_18], rax
0x18000170c  mov     rax, [rsp+98h+arg_30]
0x180001714  xor     r9d, r9d
0x180001717  mov     [r11-28h], rax
0x18000171b  xor     r8d, r8d
0x18000171e  mov     rax, [rsp+98h+arg_28]
0x180001726  mov     qword ptr [r11-20h], 8
0x18000172e  mov     qword ptr [r11-30h], 10h
0x180001736  mov     qword ptr [r11-40h], 4
0x18000173e  mov     rcx, [rax]
0x180001741  mov     rax, [rsp+98h+arg_20]
0x180001749  mov     [r11-48h], rax
0x18000174d  lea     rax, [r11-68h]
0x180001751  mov     [r11-38h], rcx
0x180001755  lea     rcx, dword_18001C010
0x18000175c  mov     [r11-70h], rax
0x180001760  mov     [rsp+98h+var_78], 5
0x180001768  call    _tlgWriteTransfer_EventWriteTransfer
0x18000176d  mov     rcx, [rsp+98h+var_18]
0x180001775  xor     rcx, rsp; StackCookie
0x180001778  call    __security_check_cookie
0x18000177d  add     rsp, 98h
0x180001784  retn
```
