# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)

- ea: `0x140001b5c`
- end: `0x140001bc5`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `105`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000ab00`
- `0x14000abc0`

## callees

- `0x1400025b8`
- `0x1400033b0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  _QWORD v7[8]; // [rsp+30h] [rbp-58h] BYREF

  v7[6] = a6;
  v7[4] = a5;
  v7[7] = 4;
  v7[5] = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, a4, 4, v7);
}

```

## disassembly

```asm
0x140001b5c  mov     r11, rsp
0x140001b5f  sub     rsp, 88h
0x140001b66  mov     rax, cs:__security_cookie
0x140001b6d  xor     rax, rsp
0x140001b70  mov     [rsp+88h+var_18], rax
0x140001b75  mov     rax, [rsp+88h+arg_28]
0x140001b7d  mov     r10d, 4
0x140001b83  mov     [r11-28h], rax
0x140001b87  mov     rax, [rsp+88h+arg_20]
0x140001b8f  mov     [r11-38h], rax
0x140001b93  lea     rax, [r11-58h]
0x140001b97  mov     [r11-60h], rax
0x140001b9b  mov     [r11-68h], r10d
0x140001b9f  mov     [r11-20h], r10
0x140001ba3  mov     qword ptr [r11-30h], 8
0x140001bab  call    _tlgWriteTransfer_EventWriteTransfer
0x140001bb0  mov     rcx, [rsp+88h+var_18]
0x140001bb5  xor     rcx, rsp; StackCookie
0x140001bb8  call    __security_check_cookie
0x140001bbd  add     rsp, 88h
0x140001bc4  retn
```
