# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x140001360`
- end: `0x1400013e5`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z`
- size: `133`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x140008710`
- `0x1400087c0`
- `0x140008ad0`
- `0x140008b80`
- `0x14000a718`
- `0x14000a7b8`
- `0x140019160`
- `0x140019210`
- `0x140019680`
- `0x140019a70`
- `0x140019b20`

## callees

- `0x14000176c`
- `0x140002600`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  _QWORD v8[10]; // [rsp+30h] [rbp-68h] BYREF

  v8[8] = a7;
  v8[6] = a6;
  v8[4] = a5;
  v8[9] = 4;
  v8[7] = 4;
  v8[5] = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, a4, 5, v8);
}

```

## disassembly

```asm
0x140001360  mov     r11, rsp
0x140001363  sub     rsp, 98h
0x14000136a  mov     rax, cs:__security_cookie
0x140001371  xor     rax, rsp
0x140001374  mov     [rsp+98h+var_18], rax
0x14000137c  mov     rax, [rsp+98h+arg_30]
0x140001384  mov     [r11-28h], rax
0x140001388  mov     rax, [rsp+98h+arg_28]
0x140001390  mov     [r11-38h], rax
0x140001394  mov     rax, [rsp+98h+arg_20]
0x14000139c  mov     [r11-48h], rax
0x1400013a0  lea     rax, [r11-68h]
0x1400013a4  mov     [r11-70h], rax
0x1400013a8  mov     [rsp+98h+var_78], 5
0x1400013b0  mov     qword ptr [r11-20h], 4
0x1400013b8  mov     qword ptr [r11-30h], 4
0x1400013c0  mov     qword ptr [r11-40h], 8
0x1400013c8  call    _tlgWriteTransfer_EventWriteTransfer
0x1400013cd  mov     rcx, [rsp+98h+var_18]
0x1400013d5  xor     rcx, rsp; StackCookie
0x1400013d8  call    __security_check_cookie
0x1400013dd  add     rsp, 98h
0x1400013e4  retn
```
