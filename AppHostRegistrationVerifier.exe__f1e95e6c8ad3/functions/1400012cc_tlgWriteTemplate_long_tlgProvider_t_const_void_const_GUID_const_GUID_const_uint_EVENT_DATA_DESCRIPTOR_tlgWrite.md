# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x1400012cc`
- end: `0x140001354`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z`
- size: `136`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x14000e348`
- `0x14000e430`
- `0x14000e660`
- `0x14000e890`

## callees

- `0x140001b78`
- `0x140002210`

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
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 5, v8);
}

```

## disassembly

```asm
0x1400012cc  mov     r11, rsp
0x1400012cf  sub     rsp, 98h
0x1400012d6  mov     rax, cs:__security_cookie
0x1400012dd  xor     rax, rsp
0x1400012e0  mov     [rsp+98h+var_18], rax
0x1400012e8  mov     rax, [rsp+98h+arg_30]
0x1400012f0  xor     r9d, r9d
0x1400012f3  mov     [r11-28h], rax
0x1400012f7  mov     rax, [rsp+98h+arg_28]
0x1400012ff  mov     [r11-38h], rax
0x140001303  mov     rax, [rsp+98h+arg_20]
0x14000130b  mov     [r11-48h], rax
0x14000130f  lea     rax, [r11-68h]
0x140001313  mov     [r11-70h], rax
0x140001317  mov     [rsp+98h+var_78], 5
0x14000131f  mov     qword ptr [r11-20h], 4
0x140001327  mov     qword ptr [r11-30h], 4
0x14000132f  mov     qword ptr [r11-40h], 8
0x140001337  call    _tlgWriteTransfer_EventWriteTransfer
0x14000133c  mov     rcx, [rsp+98h+var_18]
0x140001344  xor     rcx, rsp; StackCookie
0x140001347  call    __security_check_cookie
0x14000134c  add     rsp, 98h
0x140001353  retn
```
