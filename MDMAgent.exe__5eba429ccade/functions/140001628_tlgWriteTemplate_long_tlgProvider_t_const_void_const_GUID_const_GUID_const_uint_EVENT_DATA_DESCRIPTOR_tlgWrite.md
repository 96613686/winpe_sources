# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)

- ea: `0x140001628`
- end: `0x140001691`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `105`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140016980`
- `0x140016a18`
- `0x140016ab0`

## callees

- `0x140001f48`
- `0x140002930`

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
0x140001628  mov     r11, rsp
0x14000162b  sub     rsp, 88h
0x140001632  mov     rax, cs:__security_cookie
0x140001639  xor     rax, rsp
0x14000163c  mov     [rsp+88h+var_18], rax
0x140001641  mov     rax, [rsp+88h+arg_28]
0x140001649  mov     r10d, 4
0x14000164f  mov     [r11-28h], rax
0x140001653  mov     rax, [rsp+88h+arg_20]
0x14000165b  mov     [r11-38h], rax
0x14000165f  lea     rax, [r11-58h]
0x140001663  mov     [r11-60h], rax
0x140001667  mov     [r11-68h], r10d
0x14000166b  mov     [r11-20h], r10
0x14000166f  mov     qword ptr [r11-30h], 8
0x140001677  call    _tlgWriteTransfer_EventWriteTransfer
0x14000167c  mov     rcx, [rsp+88h+var_18]
0x140001681  xor     rcx, rsp; StackCookie
0x140001684  call    __security_check_cookie
0x140001689  add     rsp, 88h
0x140001690  retn
```
