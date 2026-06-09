# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &)

- ea: `0x1400012b0`
- end: `0x140001342`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `146`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140007dcc`

## callees

- `0x140001498`
- `0x1400134a0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(
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
  v8[9] = 8;
  v8[7] = 1;
  v8[5] = 4;
  return tlgWriteTransfer_EventWriteTransfer(&dword_140019000, a2, 0, 0, 5, v8);
}

```

## disassembly

```asm
0x1400012b0  mov     r11, rsp
0x1400012b3  sub     rsp, 98h
0x1400012ba  mov     rax, cs:__security_cookie
0x1400012c1  xor     rax, rsp
0x1400012c4  mov     [rsp+98h+var_18], rax
0x1400012cc  mov     rax, [rsp+98h+arg_30]
0x1400012d4  lea     rcx, dword_140019000
0x1400012db  mov     [r11-28h], rax
0x1400012df  xor     r9d, r9d
0x1400012e2  mov     rax, [rsp+98h+arg_28]
0x1400012ea  xor     r8d, r8d
0x1400012ed  mov     [r11-38h], rax
0x1400012f1  mov     rax, [rsp+98h+arg_20]
0x1400012f9  mov     [r11-48h], rax
0x1400012fd  lea     rax, [r11-68h]
0x140001301  mov     [r11-70h], rax
0x140001305  mov     [rsp+98h+var_78], 5
0x14000130d  mov     qword ptr [r11-20h], 8
0x140001315  mov     qword ptr [r11-30h], 1
0x14000131d  mov     qword ptr [r11-40h], 4
0x140001325  call    _tlgWriteTransfer_EventWriteTransfer
0x14000132a  mov     rcx, [rsp+98h+var_18]
0x140001332  xor     rcx, rsp; StackCookie
0x140001335  call    __security_check_cookie
0x14000133a  add     rsp, 98h
0x140001341  retn
```
